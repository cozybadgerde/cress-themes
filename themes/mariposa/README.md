# Mariposa

Mariposa is a broadsheet theme for Cress. It suits restaurants, cafés, food
trucks, and other businesses that post menus, opening hours, and short news.
Pages use a serif face on light newsprint, with thick and thin rules between
sections.

It requires Cress 1.x, from 1.0.0. Installation is described in the
[collection README](../../README.md#install-a-theme).

## Pages

- Landing pages show a large headline, the dates, and a title image. The
  first paragraph is shown large. The rest of the text stays in a single
  reading column, with wider section headings, tables, and images.
  The second paragraph starts with a drop cap, and every paragraph that
  contains only a link becomes a button.
- Ordinary pages show a large headline, the page's `excerpt` as an italic
  standfirst when it's set, and the dates between rules. A title image
  appears wide, followed by the text in a single reading column.
- List pages show entries in ruled columns in the order Cress provides. The
  first entry on each page spans the full width. On wide screens its image
  sits beside the text.
- The not-found page shows a large 404 with a link home.

Landing pages use stacked sections to avoid Safari's multi-column rendering
issues with spanning headings. Tables get heavy header rules and aligned
numbers, which suits menus and price lists. Block quotes become centered
pull quotes between rules.

## Images

Mariposa crops title images to fixed shapes: 4:3 on small screens and 2:1 on
wide screens for landing pages, 16:9 on articles, 3:2 for list entries, and
21:9 on list pages. Use `focus` in the image settings to keep the important
part in view. Images inside the text keep their proportions.

## Color

Text is near-black on off-white paper. The default accent is printer's red,
`#b3261e`, used for links, the current menu item, and list bullets. Set
`[brand] color` in `cress.toml` to replace it. The accent appears as text on
the paper, so choose a color with at least 4.5:1 contrast against white. Cress
warns when it's lower.

## Languages and settings

Mariposa includes labels for English (`en`) and German (`de`). It reads no
`[theme.custom]` settings.

Text uses serif system fonts such as Iowan Old Style, Charter, Cambria, and
Georgia, so it looks slightly different on macOS, Windows, Android, and
Linux.
