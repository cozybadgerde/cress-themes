# Iris

Iris is an image-first portfolio theme for Cress. It suits photographers,
artists, and tattoo studios. Pages use street-poster typography, acid-yellow
fields, black ink sections, and tightly grouped images at different scales.

It requires Cress 1.x, from 1.0.0. Installation is described in the
[collection README](../../README.md#install-a-theme).

## Pages

- Landing pages put a large uppercase title above an uncropped title image.
  An optional `excerpt` sits in a separate black panel beside the image on
  wide screens. The body uses an asymmetric poster layout on black.
- List pages form a portfolio of differently sized image plates. Entries
  stay in the order Cress provides, with titles, dates, captions, and excerpts
  visible without hovering. Entries without images still show their text.
- Ordinary pages give each project a title, optional excerpt, large title
  image, and a reading column. Body images can extend beyond the text.
- The not-found page includes a link home.

Images always keep their original proportions. Iris does not crop title,
list, or body images, so the image `focus` setting has no effect. It adds
no carousel, lightbox, or JavaScript.

## Build a portfolio

Create ordinary pages in a section such as `work/`. Give each page an
`[image]` and an optional `excerpt`. Add a `work/list.md` with `type = "list"`
to collect the projects. Link to its published URL, `/work/list/`, in the
site navigation.

A landing page cannot automatically collect projects in Cress 1.0.0. Add
your chosen images and project links to its Markdown content instead. Use
image captions for materials, dates, credits, and project links.

## Color and typography

Iris uses acid yellow, near-black ink, and light reading sheets. Set
`[brand] color` in `cress.toml` to replace link color on light reading sheets.
Check its contrast against the light background. The poster yellow stays
fixed so navigation and dark-section links retain their contrast.

Headings use the locally bundled Anton by Vernon Adams, licensed under the
[SIL Open Font License 1.1](public/fonts/ANTON-OFL.txt).
Other text uses system sans-serif fonts. No external font service is needed.
The font retains its own license; the theme code uses the collection license.

Portfolio titles reverse into yellow on hover and keyboard focus. The color
transition becomes immediate when the visitor prefers reduced motion.

## Languages and settings

Iris includes labels for English (`en`) and German (`de`). It reads no
`[theme.custom]` settings. Navigation labels and project content come from
the site.
