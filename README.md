# Cress themes

Themes for [Cress](https://github.com/cozybadgerde/cress), maintained by
Cozy Badger.

| Theme | For | Version |
|-------|-----|---------|
| [Foxglove](themes/foxglove/) | Publications, journals, and businesses that write a lot. Bold magazine layout with color blocks and an editorial grid. | 0.1.0 |
| [Bluebell](themes/bluebell/) | Small businesses, products, and personal sites. Rounded glass panels over soft color fields, in light and dark. | 0.1.0 |

Each theme is a complete, standalone package. Installing one doesn't require
the others.

## Install a theme

Cress reads local themes from the `themes/` folder of your site. To install
Foxglove into a site at `my-site/`:

```sh
git clone https://github.com/cozybadgerde/cress-themes.git
mkdir -p my-site/themes
cp -R cress-themes/themes/foxglove my-site/themes/
```

Then select it in `my-site/cress.toml`:

```toml
[theme]
name = "foxglove"
```

Preview the result with `cress site preview my-site`. Copy the folder as real
files: Cress rejects symlinks inside a site's `themes/` folder.

To update a theme, replace its whole folder with the new version. Don't merge
the files.

Each theme's `theme.json` lists the Cress versions it supports, and its README
lists its languages and settings. The
[Cress user guide](https://github.com/cozybadgerde/cress/blob/trunk/docs/USER.md)
covers sites and theme selection.

## Develop a theme

Follow the
[theme developer guide](https://github.com/cozybadgerde/cress/blob/trunk/docs/THEMES.md).
To try a theme from this repository, create a test site and copy the theme
into it:

```sh
mkdir -p tmp
cress site init tmp/demo
mkdir -p tmp/demo/themes
cp -R themes/foxglove tmp/demo/themes/
```

Set `name = "foxglove"` in `tmp/demo/cress.toml` and run
`cress site preview tmp/demo`. Copy the theme again after each change. The
`tmp/` folder is ignored by Git.

Check every page type with real content: the landing page, a list with and
without images, a long article, `/tour/`, and `404.html`. Check narrow and
wide windows and keyboard focus.

## License

The themes are available under the [BSD 3-Clause License](LICENSE).
