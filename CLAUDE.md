# base015 design — instructions for Claude

**Use the design system in [`DESIGN.md`](./DESIGN.md) ("Base015 — soft charcoal, one signal") for everything you design or build for base015**: artifacts, Design canvases, slides, web pages, portal and website UI.

Key rules (full spec in `DESIGN.md`):

- Dark only, soft charcoal rather than black. Canvas `#1C1C1A`, cards `#262624`, raised/interactive surfaces `#31312E`. Separate surfaces with that value step, never with shadows.
- Text Ivory `#F4F4F0` (primary, same as the logo letters) and Ash `#C2C2BB` (muted). Borders: Slate `#6E6E69`, Mist `#E2E2DC`. Never `#FFFFFF` for text.
- **Signal Yellow `#FFCB00` is the only accent.** Use it as a fill only for the single primary action per view (hover `#FFD633`, pressed `#E6B700`). Text on yellow is always Ink `#0E0E0E`, never white.
- Other uses of yellow: a small 5–6px dot for active/new/live (echoing the logo's period), focus rings (2px, offset 3px), short yellow labels on the tint `rgba(255,203,0,0.14)`. No blue and no second accent.
- Headings at weight 480 (530 max for the largest display), never 600/700. Body 16px / 400 / 1.5.
- Pill radius (32–40px) for buttons, inputs, nav items and tags; 12px for cards; 4px for structural elements only.
- 4px spacing base, 32px card padding, 1200px max content width, 112px section padding on long pages.
- Pages follow the sample homepage (see "Layout" in `DESIGN.md`): headlines ending in a yellow full stop, stacked one-word-per-line section labels with a yellow dot, big stat rows, canvas/card bands alternating, at most two full Signal Yellow bands (proof moment and final call to action), and the giant "Base015." wordmark in the footer.

Fonts: `arcadia` and `arcadiaDisplay` are not publicly available. Until base015 supplies its own files, use these substitutes from Google Fonts:

- Body / UI: **Inter** (variable, so weights 360 / 420 / 480 work).
- Display: **Archivo** with `font-stretch: 112%` (wide-set, close to Söhne Breit).
- Logo only: **Inter Tight** 600.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@62..125,100..900&family=Inter:wght@100..900&family=Inter+Tight:wght@600&display=swap">
```

## Logo (use these exact parameters)

Wordmark **"Base015."**, where the period is part of the logo.

- Inter Tight SemiBold 600, letter-spacing -0.035em, written exactly "Base015." (capital B, the rest lowercase).
- Letters: Ink `#0E0E0E` on light backgrounds, `#F4F4F0` on dark backgrounds (including the `#1C1C1A` UI).
- Period: Signal Yellow `#FFCB00` in both light and dark.
- About 18px in the site header and body size (16px) in the footer. It scales freely as a vector.
- Markup: `<span style="font-family:'Inter Tight';font-weight:600;letter-spacing:-0.035em;color:#F4F4F0">Base015<span style="color:#FFCB00">.</span></span>`

App icon / compact mark (favicon, 512px app icon, Apple touch icon):

- Square with an Ink `#0E0E0E` background.
- A "B" in Paper `#FCFCFA`, Inter Tight SemiBold, set large (~70% of the width) and slightly left of centre (~6%).
- A Signal Yellow `#FFCB00` dot in the bottom-right corner, about 17% of the icon width, inset ~9%.

Logo backgrounds outside the product: Paper `#FCFCFA` (light) and Ink `#0E0E0E` (dark).

Reference canvas (System page: logo, foundations, components, and the sample homepage in two parts; Explorations page: how the accent, background and layout were chosen): https://claude.ai/artifact/6iYh73GtszfrSt9WC2coxs
