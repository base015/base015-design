# base015 design — instructions for Claude

**Use the design system in [`DESIGN.md`](./DESIGN.md) ("Mercury — alpine banking at blue hour") for everything you design or build for base015**: artifacts, Design canvases, slides, web pages, portal and website UI.

Key rules (full spec in `DESIGN.md`):

- Dark only. Canvas `#171721`, cards `#1e1e2a`, interactive surfaces `#272735`. Separate with that value step, never shadows.
- Text Ivory `#ededf3` (primary) and Ash `#c3c3cc` (muted). Never `#ffffff` for body text; white is only for text on cobalt.
- Cobalt `#5266eb` is the only accent, and only for the single primary action on a page. No other bright colors.
- Headings at weight 480 (530 max for the largest display), never 600/700. Body 16px / 400 / 1.5.
- Pill radius (32–40px) for buttons, inputs, nav items and tags; 12px for cards; 4px for structural elements only.
- 4px spacing base, 32px card padding, 72px between sections, 1200px max content width.

Fonts: `arcadia` and `arcadiaDisplay` are not publicly available. Until base015 supplies its own files, use these substitutes from Google Fonts:

- Body / UI: **Inter** (variable, so weights 360 / 420 / 480 work).
- Display: **Archivo** with `font-stretch: 112%` (wide-set, close to Söhne Breit).

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@62..125,100..900&family=Inter:wght@100..900&display=swap">
```

## Logo (use these exact parameters; the logo overrides the Mercury palette)

Wordmark **"Base015."**, where the period is part of the logo.

- Inter Tight SemiBold 600 (Google Fonts), letter-spacing -0.035em, written exactly "Base015." (capital B, the rest lowercase).
- Letters: Ink `#0E0E0E` on light backgrounds, `#F4F4F0` on dark backgrounds (including the Onyx `#171721` UI).
- Period: Signal Yellow `#FFCB00` in both light and dark. This yellow belongs to the logo only. It is not a second UI accent; Cobalt stays the only UI accent.
- About 18px in the site header and body size (16px) in the footer. It scales freely as a vector.
- Markup: `<span style="font-family:'Inter Tight';font-weight:600;letter-spacing:-0.035em;color:#F4F4F0">Base015<span style="color:#FFCB00">.</span></span>`

App icon / compact mark (favicon, 512px app icon, Apple touch icon):

- Square with an Ink `#0E0E0E` background.
- A "B" in Paper `#FCFCFA`, Inter Tight SemiBold, set large and slightly left of centre.
- A Signal Yellow `#FFCB00` dot in the bottom-right corner, about 17% of the icon width.

Logo backgrounds: Paper `#FCFCFA` (light) and Ink `#0E0E0E` (dark).

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter+Tight:wght@600&display=swap">
```

Reference canvas (logo, foundations, components, sample page): https://claude.ai/artifact/6iYh73GtszfrSt9WC2coxs
