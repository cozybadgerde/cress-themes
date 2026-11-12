# Developer guide

This guide covers working on the themes in this repository. For theme
structure, templates, and settings, follow the
[Cress theme developer guide](https://github.com/cozybadgerde/cress/blob/trunk/docs/THEMES.md).

Run the commands below from the repository root.

## Preview a theme

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

## Run the checks

Before sending a change, run the checks with [mise](https://mise.jdx.dev/):

```sh
mise run check
```

They lint Markdown, check spelling and TOML, and build every theme with
Cress 1.0.0 in English and German. CI runs the same checks. Format TOML files
with `mise run fmt`.

The [release guide](RELEASE.md) covers packaging, signing, and publishing.
