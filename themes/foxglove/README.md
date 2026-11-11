# Foxglove

Foxglove is a magazine theme for Cress. It suits newsletters, small
publications, and businesses that publish long articles. Headlines are
heavy, scale changes are large, and solid color blocks mark the main
moments.

It requires Cress 1.x, from 1.0.0. Installation is described in the
[collection README](../../README.md#install-a-theme).

## Pages

- **Landing pages** place the title in a full-width color block. A title image
  overhangs the block's lower edge. The first paragraph is shown large, and
  every paragraph that contains only a link becomes a button.
- **Ordinary pages** read like articles: a large headline, the page's
  `excerpt` as a standfirst when it's set, and the dates. A title image appears
  full width, followed by the text in a reading column.
- **List pages** show entries in a grid in the order Cress provides. The first
  entry on each page spans the full width. Entries without an image become
  solid color cards, so a list works without photographs.
- **The not-found page** shows a large 404 in a color block with a link home.

Block quotes become large pull quotes. Use them for short, quotable lines.

## Images

Foxglove crops title images to fixed shapes: 4:3 on landing pages and list
cards, 3:2 for a lead entry, and 16:9 on articles. Use `focus` in the image
settings to keep the important part in view. Images inside the text keep
their proportions.

## Color

The default accent is foxglove magenta, `#a3195b`. Set `[brand] color` in
`cress.toml` to replace it. The accent appears as text on the light
background and as the background behind white text, so choose a color with at
least 4.5:1 contrast against white. Cress warns when it's lower.

## Languages and settings

Foxglove includes labels for English (`en`) and German (`de`). It reads no
`[theme.custom]` settings.

Headlines use the system font of each device at its heaviest weight. They
look slightly different on macOS, Windows, Android, and Linux.
