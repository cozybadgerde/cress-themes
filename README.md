# Cress themes

Themes for [Cress](https://github.com/cozybadgerde/cress), maintained by
Cozy Badger.

| Theme | For | Version |
|-------|-----|---------|
| [Foxglove](themes/foxglove/) | Publications, journals, and businesses that write a lot. Bold magazine layout with color blocks and an editorial grid. | 0.1.0 |
| [Bluebell](themes/bluebell/) | Small businesses, products, and personal sites. Rounded glass panels over soft color fields, in light and dark. | 0.1.0 |
| [Mariposa](themes/mariposa/) | Restaurants, cafés, and food trucks. Classic broadsheet with serif type, ruled sections, and menu tables. | 0.1.0 |
| [Iris](themes/iris/) | Photographers, artists, and tattoo studios. Bold street-poster portfolio with acid-yellow fields and uncropped artwork. | 0.1.0 |
| [Woodruff](themes/woodruff/) | Small software and product companies. Soft forest colors, a frosted hero card, and double-framed panels. | 0.1.0 |

Each theme is a standalone package. Installing one doesn't require the others.
The [themes overview](docs/themes.md) has a screenshot of each.

## Install a theme

Cress reads local themes from the `themes/` folder of your site. To install
Foxglove into a site at `my-site/`:

```sh
curl -fLO https://github.com/cozybadgerde/cress-themes/releases/latest/download/foxglove.zip
mkdir -p my-site/themes
unzip foxglove.zip -d my-site/themes
```

Then select it in `my-site/cress.toml`:

```toml
[theme]
name = "foxglove"
```

Preview the result with `cress site preview my-site`. The archive contains
the complete theme folder as real files; Git is not required.

To update a theme, replace its whole folder with the new version. Don't merge
the files. Use the same download URL with another theme's name to install it.
The `latest` URL becomes available after the first final release is published.
For prereleases or older versions, download from the
[releases page](https://github.com/cozybadgerde/cress-themes/releases).

Collection releases and individual themes have independent versions.
Cress compatibility comes from each theme's `theme.json`, not the collection
version. The [release guide](docs/RELEASE.md) explains versioning and
signature verification.

Each theme's `theme.json` lists the Cress versions it supports, and its README
lists its languages and settings. The
[Cress user guide](https://github.com/cozybadgerde/cress/blob/trunk/docs/USER.md)
covers sites and theme selection.

## Documentation

- [Themes overview](docs/themes.md): screenshots and details for each theme.
- [Developer guide](docs/DEVELOPER.md): preview themes and run the checks.
- [Release guide](docs/RELEASE.md): sign tags, publish releases, and verify
  assets.
- [Cress user guide](https://github.com/cozybadgerde/cress/blob/trunk/docs/USER.md):
  create, configure, preview, and build a site.
- [Cress theme developer guide](https://github.com/cozybadgerde/cress/blob/trunk/docs/THEMES.md):
  theme structure, templates, and settings.

## License

The themes are available under the [BSD 3-Clause License](LICENSE).
