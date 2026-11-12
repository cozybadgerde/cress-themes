# Release guide

Run the commands below from the repository root. The
[developer guide](DEVELOPER.md) covers previewing themes and running checks.

## Versioning

The collection uses SemVer tags, starting with `v0.1.0-rc.1` and `v0.1.0`.
Its version is independent of the Cress version. Each theme declares its
supported Cress major and minimum version in `theme.json`; the checks build
all themes against the Cress version pinned in `mise.toml`.

Use a collection minor release for a new theme or a visible theme change,
and a patch release for fixes only. A 0.x release does not promise a stable
1.0 API. Each theme keeps its own SemVer in `theme.json`. Increase it when
that theme changes, leave unchanged themes alone, and describe breaking
theme changes in the release notes.

The workflow accepts full SemVer, including prerelease identifiers and
build metadata. Build metadata does not affect version precedence.

For comparison, it selects the highest lower collection version whose tag
is reachable from the tagged commit, including prereleases on the same
commit. It ignores unrelated tags and higher collection versions. Changed
themes must have a higher version than in that baseline. New themes are
listed as added; with no baseline, all themes are added.

## Create a prerelease draft

Commit the changes and push the branch before tagging. With a Git signing
key configured, create and push a signed prerelease tag:

```sh
git push origin trunk
git tag -s v0.1.0-rc.1 -m "Release v0.1.0-rc.1"
git push origin v0.1.0-rc.1
```

The [Release workflow](../.github/workflows/release.yml) runs the checks,
validates versions, creates one ZIP archive per theme and a `checksums.txt`
file, signs each asset with keyless Cosign, verifies the signatures, and
creates a GitHub prerelease draft. The first release includes Bluebell,
Foxglove, Iris, Mariposa, and Woodruff.

Each asset has an accompanying `.sigstore.json` verification bundle.
Signatures identify the workflow and tag through GitHub Actions, rather
than a maintainer's personal signing key. Signing records are public in
Sigstore's transparency log.

### Review and publish

Open the draft on the
[releases page](https://github.com/cozybadgerde/cress-themes/releases).
Its notes list each theme, its version, and whether it was added, changed,
or unchanged since the baseline tag. Add explanations of visible changes
and any breaking theme changes.

Download and verify the assets, extract each ZIP, and build a test site
with a supported Cress version. Draft assets require maintainer access;
the GitHub CLI can download them using the draft's tag. Then publish the
prerelease through GitHub, or run:

```sh
gh release edit v0.1.0-rc.1 --repo cozybadgerde/cress-themes \
  --draft=false --prerelease --latest=false
```

## Promote a prerelease

After validating the prerelease, sign off the final release with a second
signed tag on the same commit, even if your branch has moved:

```sh
git tag -s v0.1.0 'v0.1.0-rc.1^{commit}' -m "Release v0.1.0"
git push origin v0.1.0
```

This creates a separate final-release draft and leaves the prerelease
available. Runs are scoped to tags, not commits, so both tags trigger a
release. No theme version bump is needed when promoting the same commit.
Theme contents and versions stay the same; signatures identify the new tag.
Push each tag explicitly rather than all local tags.

Review the final draft, then publish it as the latest release:

```sh
gh release edit v0.1.0 --repo cozybadgerde/cress-themes --draft=false --latest
```

Only tags with a prerelease suffix before any build metadata are marked as
prereleases. Drafts are never made latest automatically.

## Release packages

Archives have versionless names such as `foxglove.zip`. Each contains the
complete `foxglove/` folder as real files, including its unchanged
`theme.json`, the collection license, and any bundled font licenses.
The workflow packages committed files from the tagged commit using `zip`,
then generates `checksums.txt` with `sha256sum`.

For installation, extract one archive into your site's `themes/` folder.
When updating, replace the whole theme folder rather than merging files.
Published final releases support stable download links such as:

```text
https://github.com/cozybadgerde/cress-themes/releases/latest/download/foxglove.zip
```

Use a specific release's download link to pin a collection version.
GitHub's automatic source archives contain the repository, not a single
installable theme package.

## Verify a release asset

Install [Cosign](https://docs.sigstore.dev/cosign/system_config/installation/)
3.x and the GitHub CLI. Download and verify Foxglove's final release archive:

```sh
tag=v0.1.0
asset=foxglove.zip
gh release download "$tag" --repo cozybadgerde/cress-themes \
  --pattern "$asset" --pattern "$asset.sigstore.json"
cosign verify-blob "$asset" --bundle "$asset.sigstore.json" \
  --certificate-identity \
  "https://github.com/cozybadgerde/cress-themes/.github/workflows/release.yml@refs/tags/$tag" \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com
```

Use the prerelease tag to verify prerelease assets. The same command works
for `checksums.txt` with its corresponding bundle. To verify checksums after
downloading all ZIP files and verifying the checksum file's signature, run:

```sh
sha256sum -c checksums.txt
```
