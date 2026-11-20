# base015 design — instructions for Claude

**Use the design system in [`DESIGN.md`](./DESIGN.md) (v3, "Cinematic and dark-led, one yellow signal") for everything you design or build for Base015**: the marketing website, the client portal, artifacts, Design canvases, slides, emails and documents. Load the shared tokens from [`tokens/base015.css`](./tokens/base015.css) rather than restating hex values.

v3 comes from the website redesign (`base015-website`, `docs/redesign/BRIEF.md`) and replaces v2 ("Editorial paper").

## The rules that matter most

- **Dark-led.** Ink `#0E0E0E` canvas, `#161615` cards, Ivory `#F4F4F0` text. Paper `#FCFCFA` sections (`.surface-paper`) give rhythm. The website, slides and social are Ink by default; the portal sets `data-theme="light"` or `"dark"` (charcoal `#1C1C1A`); emails and documents are on Paper.
- **Signal Yellow `#FFCB00` is the only accent, and it is a signal**: the main button, the focus ring on dark surfaces, active states and small live dots. Always a fill with Ink on it. Never text, icons or outlines, never a large area, never yellow text on white. On Paper the focus ring is Ink.
  - One yellow button in view, paired with an outline pill. Sticky bars and menus carry no yellow: their main action is a solid pill in the text colour.
- **Type:** Archivo for headings, prices and big numbers (800 at width 115 for H1, 700 at width 112 for H2, 600 for H3); Inter for everything else. Body 17–18px on the website, 16px in the portal. **Nothing under 14px.** Both free (SIL OFL) from Google Fonts; never commit font files.
- **Shape:** fully rounded pills for buttons, 20px cards, 16px inputs and media. Icons are 16px line glyphs in a rounded square of the block's raised colour, white on Ink and Ink on Paper. Dividers at 8% opacity. **Flat:** no shadows, except portal overlays.
- **Layout:** strict 12-column grid, 1360px container, 120px between sections. Left-aligned text; paragraphs at most 60ch, leads 46ch.
- **Video-first.** Sections are built from video, photos, numbers and interaction, not paragraphs. Posters show first and motion respects reduced-motion and Save-Data.
- **Status colours** (success, warning, danger) exist only in the portal and stay muted.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@100..125,600..800&family=Inter:wght@400..600&display=swap">
```

## Never (these read as a template)

- Serif headlines, a half-italic phrase, a yellow dot or full stop after a heading.
- Eyebrow or overline labels above headings, uppercase mono labels.
- Fake UI widgets floating around a hero.
- Three equal numbered cards (01 / 02 / 03).
- Yellow cards, yellow bands or a pale-yellow wash.
- Middle-dot separators ("Half day · $600"): use icons or separate lines.
- Text links as main actions; drop shadows, chrome, bevel or clipart-style vectors.

## Logo

- Use the files in `assets/logo/`: `wordmark-on-dark.svg`, `wordmark-on-light.svg`, `wordmark.svg` (`currentColor` letters), `app-icon.svg`. The wordmark is unchanged from v2.
- As live text, only where an SVG can't go: "Base015" in Inter Tight 600, letter-spacing −0.035em, `#F4F4F0` on dark or Ink on light, followed by a "." in Signal Yellow. The logo's period is the one yellow glyph allowed.

## Content

- Voice: direct, plain-spoken, confident, local. Short sentences, no hype words.
- One heading and at most one short lead per section. Numbers beat sentences. Lists of at most six short items, with icons.
- No rhetorical questions, exclamation marks, em-dash asides, semicolon pairs, colon-then-list sentences or groups of three for rhythm. The full list is in `DESIGN.md`.
- Base015 makes video ads, monthly content and content systems for service businesses in Sacramento, Roseville and Folsom. It does **not** run or manage ads.
- Never invent stats, clients or testimonials. Leave unconfirmed numbers as visible placeholders.
- Client names, photos, logos and testimonials stay out of this public repo. They live in the private website repo and the private canvas.

## Reference

The live reference for v3 is the website's `redesign` branch (`src/app/globals.css` and `src/components/`).

The private canvases in the Base015 claude.ai account still show v2 and need redrawing before they are used for new work:
- Design System: https://claude.ai/artifact/LESK5APUsESsExz394RH36
- Reference canvas: https://claude.ai/artifact/6iYh73GtszfrSt9WC2coxs
