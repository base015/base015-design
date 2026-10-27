# base015 design — instructions for Claude

**Use the design system in [`DESIGN.md`](./DESIGN.md) (v2, "Editorial paper, one yellow signal") for everything you design or build for Base015**: the marketing website, the client portal, artifacts, Design canvases, slides, emails and documents. Load the shared tokens from [`tokens/base015.css`](./tokens/base015.css) rather than restating hex values.

## The rules that matter most

- **Light-first.** Paper `#FCFCFA` canvas, Mist `#F3F3EF` cards, Fog `#F8F8F5` bands, Ink `#0E0E0E` text. The website is light with Ink bands for rhythm; the portal is light-first with the charcoal dark mode (`data-theme="dark"`, canvas `#1C1C1A`) as the user's choice; emails are light only.
- **Signal Yellow `#FFCB00` is the only accent, and it is a fill only, always with Ink text**, in both modes. Never text, icons, outlines or focus rings (focus rings use the text colour).
  - One yellow pill per view, always paired with a ghost pill. One yellow editorial card per page, never on a dark band. The wash `#FFF3C4` is for emphasis, never for actions.
  - The yellow dot is the motif: before section labels, on active items, and ending display headlines as a filled circle.
- **Type:** Instrument Serif for H1/H2 only (400, never bold, 40px+, one italic phrase allowed); Inter for body and UI (17px website, 16px portal); Inter Tight for prices, stats and the wordmark; Space Mono for uppercase labels. All free (SIL OFL) from Google Fonts; never commit font files.
- **Shape:** pills for buttons and chips, 24px cards, 16px inputs and small cards, 12px media. **Flat:** no shadows, except the floating hero artifacts (`--shadow-artifact`) and portal overlays.
- **Status colours** (success, warning, danger) exist only in the portal and stay muted.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Inter+Tight:wght@100..900&family=Instrument+Serif:ital@0;1&family=Space+Mono:wght@400;700&display=swap">
```

## Logo

- Use the files in `assets/logo/`: `wordmark-on-dark.svg`, `wordmark-on-light.svg`, `wordmark.svg` (`currentColor` letters), `app-icon.svg`.
- As live text: "Base015" in Inter Tight 600, letter-spacing −0.035em, Ink on light or `#F4F4F0` on dark, followed by a "." in Signal Yellow. The logo's period is the one yellow glyph allowed. Headlines are the serif; the wordmark stays Inter Tight on purpose.

## Content

- Voice: direct, plain-spoken, confident, local. Short sentences, no hype words.
- Base015 makes video ads, monthly content and content systems for service businesses in Sacramento, Roseville and Folsom. It does **not** run or manage ads.
- Never invent stats, clients or testimonials. Leave unconfirmed numbers as visible placeholders.
- Client names, photos, logos and testimonials stay out of this public repo. They live in the private website repo and the private canvas.

## Reference

Design System (private, in the Base015 claude.ai account; use it for new Design canvases): https://claude.ai/artifact/LESK5APUsESsExz394RH36

Reference canvas (private): https://claude.ai/artifact/6iYh73GtszfrSt9WC2coxs
- **System page:** v2 foundations, components, the sample homepage in two parts, and the logo.
- **v1 (archived)** and **Explorations** pages: the earlier dark system and how the accent, background and layout were chosen.
