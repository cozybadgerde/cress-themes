# Bluebell

Bluebell is a rounded glass theme for Cress. It suits small businesses,
products, and personal sites. Content sits on frosted, translucent panels
that scroll over fixed color fields made from the brand color. It follows
the visitor's light or dark setting.

It requires Cress 1.x, from 1.0.0. Installation is described in the
[collection README](../../README.md#install-a-theme).

## Pages

- Landing pages open with a hero card for the title. A title image sits
  beside it in a rounded frame on wide screens and below it on narrow ones.
  The body follows on one wide panel. The first paragraph is shown large, and
  every paragraph that contains only a link becomes a pill button.
- Ordinary pages are a single panel: headline, the page's `excerpt` as a
  standfirst when it's set, date chips, a title image, and the text in a
  reading column.
- List pages show entries as an even grid of cards in the order Cress
  provides. Entries without an image get a card tinted with the accent.
- The not-found page is a compact panel with a large 404 and a link home.

The site title, logo, and main navigation share a floating bar that stays at
the top on larger screens. Without a title, logo, or main navigation, the bar
is left out.

## Images

Bluebell crops title images to fixed shapes: 4:3 on landing pages (taller on
wide screens, to match the hero card), 4:3 on list cards, 16:9 on articles,
and 21:9 on list pages. Use `focus` in the image settings to keep the
important part in view. Images inside the text keep their proportions.

## Color

The default accent is bluebell violet, `#4b4fc2`. Set `[brand] color` in
`cress.toml` to replace it. The accent colors links, buttons, the current
navigation item, and the background fields, which also take two neighboring
hues. Buttons use white text on the accent, so choose a color with at least
4.5:1 contrast against white. Cress warns when it's lower. In dark mode,
links use a lighter tint of the accent.

A logo shows on both light and dark panels, so use artwork that works on
both.

## Glass and accessibility

Panels turn solid when the browser can't blur the background or the visitor
has asked for reduced transparency. Cards lift on hover unless the visitor
prefers reduced motion. In forced-colors mode and in print, the color fields
are removed and panels get plain outlines.

## Languages and settings

Bluebell includes labels for English (`en`) and German (`de`). It reads no
`[theme.custom]` settings.

Text uses the system font of each device. Headlines use the rounded system
font where one exists, such as SF Pro Rounded in Safari on Apple devices.
Other browsers show the regular system font.
