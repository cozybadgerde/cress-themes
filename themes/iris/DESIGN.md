---
name: Iris
description: A Cress portfolio in the language of a pasted street-poster wall.
colors:
  signal: "#e5ff45"
  ink: "#171a16"
  paper: "#f3f4ed"
  muted: "#555b50"
  accent: "#913500"
  print-ink: "#000"
  syntax-keyword: "#31592e"
  syntax-string: "#7c3d26"
  syntax-comment: "#5c5f56"
typography:
  display:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "clamp(3rem, 8vw, 6rem)"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-0.015em"
  section-heading:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "clamp(2.25rem, 4vw, 3.75rem)"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-0.015em"
  subheading:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "1.875rem"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-0.015em"
  minor-heading:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "1.5rem"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-0.015em"
  small-heading:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.4
  project-title:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "clamp(2rem, 4vw, 3.5rem)"
    fontWeight: 400
    lineHeight: 1.08
    letterSpacing: "-0.015em"
  masthead:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "2.75rem"
    fontWeight: 400
    lineHeight: 1.1
  landing-lead:
    fontFamily: 'Anton, "Arial Narrow", sans-serif'
    fontSize: "clamp(2.5rem, 5vw, 4.5rem)"
    fontWeight: 400
    lineHeight: 1.1
  emphasis:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1.125rem"
    fontWeight: 700
    lineHeight: 1.45
  summary:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1.125rem"
    fontWeight: 400
    lineHeight: 1.6
  excerpt:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  pullquote:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1.5rem"
    fontWeight: 700
    lineHeight: 1.4
  footer-copy:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "0.875rem"
    fontWeight: 400
    lineHeight: 1.6
  body:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  reading:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1.125rem"
    fontWeight: 400
    lineHeight: 1.7
  navigation:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "0.875rem"
    fontWeight: 700
    lineHeight: 1.6
  caption:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "0.875rem"
    fontWeight: 400
    lineHeight: 1.5
  metadata:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "0.8125rem"
    fontWeight: 400
    lineHeight: 1.6
  code:
    fontFamily: 'ui-monospace, "SF Mono", Menlo, Consolas, monospace'
    fontSize: "0.85em"
    fontWeight: 400
  standalone-link:
    fontFamily: '"Helvetica Neue", Helvetica, Arial, sans-serif'
    fontSize: "1.125rem"
    fontWeight: 700
    lineHeight: 1.7
spacing:
  gutter: "clamp(1.25rem, 3vw, 3rem)"
  gap: "clamp(1.25rem, 3vw, 2.5rem)"
components:
  skip-link:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.signal}"
    padding: "0.75rem 1rem"
  navigation-link:
    textColor: "{colors.ink}"
    typography: "{typography.navigation}"
    height: "2.75rem"
  navigation-link-last:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.signal}"
    typography: "{typography.navigation}"
    padding: "0 1rem"
  project-title-link:
    textColor: "{colors.paper}"
    typography: "{typography.project-title}"
  project-title-link-active:
    backgroundColor: "{colors.signal}"
    textColor: "{colors.ink}"
---

# Design System: Iris

## Overview

Creative North Star: "The Pasted Poster Wall."

Iris uses the blunt, high-contrast language of pasted street posters:
acid-yellow stock, near-black ink, light reading sheets, and oversized
condensed lettering. The identity replaces the rejected quiet monograph.

Color fields and hard edges carry the visual weight. Images keep their source
proportions, while sans-serif text keeps navigation, captions, and reading
clear. Depth comes from contrast and composition rather than shadows or
decorative effects.

**Key Characteristics:**

- Acid yellow and near-black make the dominant fields.
- Locally bundled Anton gives display type its condensed silhouette.
- System sans-serif carries utility and longer reading.
- Images remain uncropped and in their supplied order.

## Colors

Signal yellow and ink establish the poster world; paper and muted text support
reading, while a restrained rust accent serves links on light sheets.

### Primary

- **Signal yellow:** The main page field, reverse text, and highlighted states.

### Secondary

- **Rust accent:** Default link color on light reading sheets. Cress's brand
  color can replace it there.
- **Syntax green:** Keywords in the optional syntax-highlighting stylesheet.
- **Syntax clay:** Strings in the optional syntax-highlighting stylesheet.

### Neutral

- **Ink:** Main text, dark poster fields, and reversed navigation.
- **Paper:** Reading sheets and text over ink fields.
- **Muted olive:** Dates and supporting metadata.
- **Print black:** Text and surfaces in print fallbacks.
- **Syntax gray:** Comments in the optional syntax-highlighting stylesheet.

**The Sheet-Scoped Accent Rule.** Keep the configurable brand color on light
reading-sheet links. Yellow remains fixed across the poster fields.

## Typography

**Display Font:** Anton, bundled locally, with Arial Narrow and sans-serif
fallbacks.
**Body Font:** Helvetica Neue, Helvetica, Arial, sans-serif.
**Label/Mono Font:** The system monospace stack, including SF Mono, for code.

**Character:** Anton is condensed, heavy, and direct. The system sans keeps
supporting text familiar and legible without competing with display type.

### Hierarchy

- **H1:** Anton 400, `clamp(3rem, 8vw, 6rem)`, line-height 1.08.
- **H2:** Anton 400, `clamp(2.25rem, 4vw, 3.75rem)`, line-height 1.08.
- **H3:** Anton 400, `1.875rem`, line-height 1.08.
- **H4:** Anton 400, `1.5rem`, line-height 1.08.
- **H5 and H6:** System sans, `1rem`, line-height 1.4.
- **Project title:** Anton 400, `clamp(2rem, 4vw, 3.5rem)`, line-height 1.08.
- **Masthead:** Anton 400, `2.75rem`, line-height 1.1.
- **Landing lead:** Anton 400, `clamp(2.5rem, 5vw, 4.5rem)`, line-height 1.1;
  uppercase and limited to `18ch`.
- **Emphasis copy:** System sans, `1.125rem`, bold, line-height 1.45.
- **Summary:** System sans, `1.125rem`.
- **Excerpt:** System sans, `1rem`.
- **Pullquote:** System sans, `1.5rem`, bold, line-height 1.4.
- **Footer copy:** System sans, `0.875rem`.
- **Body:** System sans, `1rem` at 1.6 line-height.
- **Reading:** System sans, `1.125rem` at 1.7 line-height.
- **Navigation:** System sans, `0.875rem`, bold and uppercase.
- **Captions:** System sans, `0.875rem` at 1.5 line-height.
- **Metadata:** System sans, `0.8125rem`, with tabular numerals for dates.
- **Code:** System monospace at `0.85em`.
- **Standalone link:** Bold uppercase reading text with a `3rem` minimum
  target height. Its font size is inherited from the reading measure.

**The Condensed-Display Rule.** Use bundled Anton for display roles and the
system sans for functional and reading text.

## Layout

The shared frame caps at `86rem`; long reading measures cap at `42rem`.
Responsive gutters range from `1.25rem` to `3rem`, and the main gap ranges
from `1.25rem` to `2.5rem`.

The layout uses a twelve-column grid at `48rem` and a wider composition
breakpoint at `60rem`. Narrow screens stack the same content without cropping
images. Wider layouts can offset image and text regions, but never reorder
them. Navigation wraps rather than overflowing.

**The Uncut-Image Rule.** Keep intrinsic image proportions. Do not crop or
reorder artwork to satisfy a grid.

## Elevation & Depth

Iris uses no shadows. Strong color fields, open space, and solid rules separate
regions; artwork remains free of overlays.

**The Flat-Field Rule.** Make depth with color and placement, not shadow.

## Shapes

The visual language is square-edged and planar. The implementation uses no
corner-radius tokens. Rules are solid and direct; images have no frame, mask,
or crop.

## Components

### Skip link

The skip link stays clipped until keyboard focus, then appears as an ink
rectangle with signal text. Focus outlines remain visible.

### Navigation

Navigation uses underlined, bold uppercase sans-serif links with a generous
minimum target height. The final main-navigation item reverses to an ink field
with signal text. Hover and current-page state thicken the underline.

### Project title links

Project titles use paper text on the ink field. Hover and keyboard focus
reverse the title into a signal field with ink text. The `0.18s` color
transition is removed for reduced motion; forced-colors mode retains an
underline.

## Do's and Don'ts

### Do

- **Do** use the bundled Anton face for display typography.
- **Do** preserve the acid-yellow, ink, and paper color roles.
- **Do** keep source image proportions, credits, and supplied order.
- **Do** keep links and captions visible without hover.
- **Do** provide forced-colors, print, and reduced-motion fallbacks.

### Don't

- **Don't** restore the rejected monograph styling.
- **Don't** crop, mask, overlay, or reorder artwork.
- **Don't** add decorative distressed effects or fake graffiti.
- **Don't** add shadows, mandatory animation, carousels, or autoplay.
