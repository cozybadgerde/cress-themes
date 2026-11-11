# Woodruff

Woodruff is a soft forest theme for Cress. It suits small software and
product companies. Headings use a light serif on warm linen paper, the menu
floats as a frosted pill, and images and code sit in rounded double frames.

It requires Cress 1.x, from 1.0.0. Installation is described in the
[collection README](../../README.md#install-a-theme).

## Pages

- Landing pages open with a full-width hero. The title image fills it, or a
  forest gradient made from the brand color when there's no image. A
  frosted card in the lower corner holds the title, the page's `excerpt`, and
  the dates. Below the hero, the first paragraph is shown as a large serif
  statement, and every paragraph that contains only a link becomes a button.
- Ordinary pages show a centered headline, the `excerpt` as a standfirst when
  it's set, and the dates. A title image follows in a double frame, then the
  text in a reading column.
- List pages show entries as framed cards in the order Cress provides. Entries
  without an image get a soft green card with the title at the bottom.
- The not-found page shows a frosted card with a large 404 and a link home on
  the gradient.

Set an `excerpt` on landing pages. Without one, the hero card shows only the
title and dates.

## Images

The landing hero fills its frame with the title image, so the crop depends on
the screen size. Other title images are cropped to fixed shapes: 16:9 on
articles, 21:9 on list pages, and 3:2 for list entries. Use `focus` in the
image settings to keep the important part in view. Images inside the text
keep their proportions.

The hero card stays readable over dark images. Very busy images still make
the frosted card harder to read, so prefer calm photos.

## Color

Text is dark green on linen paper. The default accent is Feldgrau, `#3c4e38`,
used for links, buttons, and the hero gradient. Set `[brand] color` in
`cress.toml` to replace it. The soft card and menu surfaces are derived from
the accent in browsers that support relative colors. The accent appears as
text on the paper, so choose a color with at least 4.5:1 contrast against
white. Cress warns when it's lower.

Woodruff has a light appearance only.

## Languages and settings

Woodruff includes labels for English (`en`) and German (`de`). It reads no
`[theme.custom]` settings.

Headings use serif system fonts such as New York, Iowan Old Style, Charter,
and Georgia. Body text uses the system sans-serif font. Both look slightly
different on macOS, Windows, Android, and Linux.
