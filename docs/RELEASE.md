# Release guide

Run the commands below from the repository root. The
[developer guide](DEVELOPER.md) covers previewing themes and running checks.

## Publish a prerelease

Start with `v0.1.0-rc.1` while validating the first release, then use `v0.1.0`
when it is ready. A 0.x release does not promise a stable 1.0 API.

Commit the changes and push the branch before tagging. With a Git signing
key configured, create and push a signed prerelease tag:

```sh
git push origin trunk
git tag -s v0.1.0-rc.1 -m "Release v0.1.0-rc.1"
git push origin v0.1.0-rc.1
```

The [Release workflow](../.github/workflows/release.yml) runs the checks,
creates one archive per theme and a `SHA256SUMS` file, signs each asset with
keyless Cosign, verifies the signatures, and publishes a GitHub prerelease.
Each asset has an accompanying `.sigstore.json` verification bundle.
Signatures identify the workflow and tag through GitHub Actions, rather
than a maintainer's personal signing key. Signing records are public in
Sigstore's transparency log.

## Promote a prerelease

After validating the prerelease, sign off the final release with a second
signed tag on the same commit, even if your branch has moved:

```sh
git tag -s v0.1.0 'v0.1.0-rc.1^{commit}' -m "Release v0.1.0"
git push origin v0.1.0
```

This creates a separate final release and leaves the prerelease available.
Runs are scoped to tags, not commits, so both tags trigger a release. A
prerelease suffix marks a GitHub prerelease; a tag without one marks a final
release and sets it as latest. Push each tag explicitly rather than all
local tags.

## Release packages

Archives are named `cress-theme-THEME-VERSION.tar.gz` and contain the theme's
folder and the collection license. The packaged `theme.json` version comes
from the tag without `v`; the committed files are unchanged. Promotion
therefore changes archive names, manifest versions, checksums, and signatures,
but preserves theme templates and assets. GitHub's automatic source archives
remain snapshots of the commit and do not have rewritten manifest versions.

The workflow packages committed files from the tagged commit using `tar`
and `jq`, then generates checksums with `sha256sum`. For installation,
extract a release archive into your site's `themes/` folder.

## Verify a release asset

Install [Cosign](https://docs.sigstore.dev/cosign/system_config/installation/)
3.x and the GitHub CLI. Download and verify Foxglove's final release archive:

```sh
tag=v0.1.0
asset=cress-theme-foxglove-${tag#v}.tar.gz
gh release download "$tag" --repo cozybadgerde/cress-themes \
  --pattern "$asset" --pattern "$asset.sigstore.json"
cosign verify-blob "$asset" --bundle "$asset.sigstore.json" \
  --certificate-identity \
  "https://github.com/cozybadgerde/cress-themes/.github/workflows/release.yml@refs/tags/$tag" \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com
```

Use the prerelease tag to verify prerelease assets. The same command works
for `SHA256SUMS` with its corresponding bundle.
