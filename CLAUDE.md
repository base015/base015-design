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

Reference canvas (foundations, components, sample page): https://claude.ai/artifact/6iYh73GtszfrSt9WC2coxs
