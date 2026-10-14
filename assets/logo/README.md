# Base015 logo files

| File | Use |
|------|-----|
| `wordmark-on-dark.svg` | Wordmark with Ivory `#F4F4F0` letters and a Signal Yellow `#FFCB00` period, for dark backgrounds |
| `wordmark-on-light.svg` | Wordmark with Ink `#0E0E0E` letters and a Signal Yellow period, for light backgrounds |
| `wordmark.svg` | Wordmark with `currentColor` letters (inherits the text colour) and a Signal Yellow period |

## How the wordmark was made

The wordmark is the live text "Base015." set in **Inter Tight SemiBold (600)** with letter-spacing **−0.035em**. The SVGs are that text converted to outlines:

- The text was shaped with HarfBuzz using the font's default features, so kerning matches the browser.
- −0.035em of tracking was applied after every glyph, as CSS `letter-spacing` does.
- The letters and the period are separate paths, so the period can stay yellow.
- The viewBox is in font units (2048 per em), cropped to the ink bounds, so set the size with `height` or `width`.

Inter Tight is © The Inter Project Authors and licensed under the SIL Open Font License 1.1. The OFL allows outlined glyphs in a logo; no font software is included here.

## App icon

The app icon (favicon, 512px app icon, Apple touch icon) is published at `https://portal.base015.com/icon.svg`: an Ink `#0E0E0E` square, a Paper `#FCFCFA` "B" outline path, and a Signal Yellow dot in the bottom-right corner. It belongs at `assets/logo/icon.svg` and should be used as-is, not redrawn.
