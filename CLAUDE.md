# base015 design — instructions for Claude

**Use the design system in [`DESIGN.md`](./DESIGN.md) for everything you design or build for Base015**: artifacts, Design canvases, slides, web pages, the client portal, emails and documents.

## The rules that matter most

- **Two modes, one palette.** Use the semantic tokens in `DESIGN.md`.
  - **Dark** (soft charcoal) is for the marketing site and the portal's dark mode: canvas `#1C1C1A`, card `#262624`, raised `#31312E`, text `#F4F4F0`, muted `#C2C2BB`.
  - **Light** (Paper & Ink) is for the client portal (light-first), all emails and documents: canvas `#FCFCFA`, card `#F3F3EF`, raised `#E8E8E3`, text `#0E0E0E`, muted `#55554F`.
- **Signal Yellow `#FFCB00` is the only accent, and it is a fill only, always with Ink `#0E0E0E` text**, in both modes.
  - Never use it for text, icons, outlines, underlines or focus rings. Focus rings use the text colour.
  - One yellow-filled action per view; at most two full yellow bands per page.
  - The yellow dot is the motif: it marks active/new/live, sits before section labels, and ends headlines as a filled circle, echoing the logo's period.
- **No shadows.** Surfaces separate by value (canvas → card → raised). Pill controls (32–40px radius), 12px cards, 4px structural corners.
- **Type** (all free, SIL OFL, from Google Fonts; never commit font files): Inter Tight for headings (560, tracking −0.02em), Inter for body (16/1.5), Space Mono for uppercase labels and numbers.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Inter+Tight:wght@100..900&family=Space+Mono:wght@400;700&display=swap">
```

## Logo

- Use the files in `assets/logo/` (outlined from Inter Tight 600): `wordmark-on-dark.svg`, `wordmark-on-light.svg`, `wordmark.svg` (`currentColor` letters).
- As live text: "Base015" in Inter Tight 600, letter-spacing −0.035em, Ink `#0E0E0E` on light or `#F4F4F0` on dark, followed by a "." in Signal Yellow `#FFCB00`. The logo's period is the one yellow glyph allowed.
- App icon: use `assets/logo/app-icon.svg` as-is (a copy of the portal's `src/app/icon.svg`). It's an Ink square with a Paper "B" and a yellow dot in the bottom-right corner.

## Content

- Voice: direct, plain-spoken, confident, local. Short sentences, no hype words.
- Base015 makes video ads, monthly content and content systems for service businesses in Sacramento, Roseville and Folsom. It does **not** run or manage ads.
- Never invent stats, clients or testimonials. Leave unconfirmed numbers as visible placeholders.
- Client names, photos, logos and testimonials stay out of this public repo. They live in the private website repo and the private canvas.

## Reference

Design System (private, in the Base015 claude.ai account; use it for new Design canvases): https://claude.ai/artifact/LESK5APUsESsExz394RH36

Reference canvas (private):
- **System page:** logo, foundations, components, modes (light & dark) and the sample homepage in two parts.
- **Explorations page:** how the accent, background and layout were chosen.

https://claude.ai/artifact/6iYh73GtszfrSt9WC2coxs
