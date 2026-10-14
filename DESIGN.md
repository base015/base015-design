# Base015 — Design System
> One signal, two modes

Base015 makes video ads and monthly content for service businesses in Sacramento, Roseville and Folsom. The system is quiet and premium: warm neutral surfaces, measured type, flat cards, pill-shaped controls. **Signal Yellow** (`#FFCB00`) is the only accent, and it is always a **fill with Ink text**, never text, icons or outlines.

It has two modes on one palette:

| Mode | Where it is used |
|------|------------------|
| **Dark** (soft charcoal) | Marketing site, portal dark mode |
| **Light** (Paper & Ink) | Client portal (light-first), every email, documents |

The structure (type scale, spacing, shapes, flat elevation) started from a "Mercury" style reference; the palette, type families and patterns are Base015's own. The reference canvas is linked from `CLAUDE.md`.

---

## Colour tokens

Use the semantic tokens. Each has a light and a dark value; components never hard-code a mode.

| Token | Role | Light | Dark |
|-------|------|-------|------|
| `--color-canvas` | Page background | `#FCFCFA` (Paper) | `#1C1C1A` (Soft charcoal) |
| `--color-card` | Cards, alternating bands, panels | `#F3F3EF` | `#262624` |
| `--color-raised` | Secondary buttons, active nav/tab pills, neutral tags, track of progress bars | `#E8E8E3` | `#31312E` |
| `--color-divider` | Hairlines, table rules | `#D6D6D0` | `#6E6E69` |
| `--color-border-strong` | Input edges (≥3:1 against canvas) | `#8A8A83` | `#8F8F8A` |
| `--color-text` | Primary text, icons, ghost-button stroke | `#0E0E0E` (Ink) | `#F4F4F0` (Ivory) |
| `--color-text-muted` | Secondary text, labels, captions | `#55554F` | `#C2C2BB` |
| `--color-accent` | Signal Yellow — fills only | `#FFCB00` | `#FFCB00` |
| `--color-accent-hover` | Primary hover | `#FFD633` | `#FFD633` |
| `--color-accent-pressed` | Primary pressed | `#E6B700` | `#E6B700` |
| `--color-on-accent` | Text and icons on any yellow fill | `#0E0E0E` | `#0E0E0E` |
| `--color-focus` | Focus ring (2px, offset 3px) | `#0E0E0E` | `#F4F4F0` |
| `--color-inverse` | Footer, media strips | `#0E0E0E` | `#0E0E0E` |

Brand constants: Ink `#0E0E0E`, Paper `#FCFCFA`, Ivory `#F4F4F0`, Signal Yellow `#FFCB00`.

Contrast (WCAG): text on canvas and card passes AA in both modes (muted text ≥6:1). Ink on yellow is 12.7:1. White on yellow is 1.5:1, so it is never used.

### Signal Yellow rules

1. **Fill only.** Yellow appears as a background or a solid shape: the primary button, the selected tab, the open FAQ icon, a "New" tag, a progress fill, a tick disc, the small status dot, a full call-to-action band. It is never used for text, icons, outlines, underlines or focus rings.
2. **Always Ink on top.** Anything placed on yellow is Ink `#0E0E0E`.
3. **One yellow-filled action per view.** Small dots, tags and tick discs don't count; buttons do.
4. **At most two full yellow bands per page**: one proof moment (a testimonial card) and the final call to action.
5. **The dot is the motif.** A 5–6px yellow dot marks active, new or live items and sits before section labels. Headlines end in a yellow dot (a filled circle about 0.15em wide), echoing the logo's period. Don't rely on the dot alone to signal state: pair it with a raised fill or a label, because yellow on Paper is low-contrast.
6. Yellow is the same in both modes. Do not darken it for light mode; keep Ink text on it.
7. No second accent and no blue. If a status system is ever needed (errors, success), define it separately with muted tones and never let it compete with yellow.

---

## Typography

All families are free and open-licence (SIL Open Font License 1.1), loaded from Google Fonts. No font files are committed to this repo.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Inter+Tight:wght@100..900&family=Space+Mono:wght@400;700&display=swap">
```

| Family | Token | Use |
|--------|-------|-----|
| **Inter Tight** | `--font-display` | Headlines, prices, big numbers, the wordmark. Weight 560 for headings (500–600 range), 600 for the logo. Letter-spacing −0.02em to −0.025em. |
| **Inter** | `--font-body` | Body, UI, buttons, inputs, tables. 400 body, 500 emphasis, 600 strong. |
| **Space Mono** | `--font-mono` | Uppercase labels, section labels, step numbers, tokens, metadata. 11–12px, +0.04em tracking. Never for sentences. |

Fallback stacks: display `'Inter Tight', 'Inter', system-ui, sans-serif`; body `'Inter', system-ui, sans-serif`; mono `'Space Mono', ui-monospace, monospace`. Emails fall back to Helvetica/Arial and Courier New.

### Type scale

| Role | Family | Size / line-height | Weight | Tracking |
|------|--------|--------------------|--------|----------|
| Display | Inter Tight | 65–92px / 1.0–1.02 (clamp on pages) | 560–600 | −0.025em |
| Heading lg | Inter Tight | 42–56px / 1.05 | 560 | −0.025em |
| Heading | Inter Tight | 32px / 1.15 | 560 | −0.02em |
| Heading sm | Inter Tight | 28px / 1.2 | 560 | −0.02em |
| Subheading | Inter | 21px / 1.35 | 500 | 0 |
| Body lg | Inter | 18px / 1.45 | 400 | 0 |
| Body | Inter | 16px / 1.5 | 400 | 0 |
| Body sm | Inter | 14px / 1.4 | 400 | 0 |
| Label | Space Mono | 12px / 1.3, uppercase | 400 | +0.04em |
| Caption | Inter | 12px / 1.5 | 400 | 0 |

---

## Space, shape, elevation

- **Spacing:** 4px base. Scale 4, 8, 12, 16, 20, 24, 32, 40, 56, 72, 112, 128.
- **Layout:** 1200px max content width, 24px side gutters. Section padding 72px, 112px on long marketing pages. Card padding 32px (28px for dense cards). Element gap 12px.
- **Radius:** 4px structural (image wells, table frames); 12px cards and panels; 32px buttons and inputs; 40px nav items, tags and ghost buttons; 50% dots and avatars.
- **Elevation:** none. No shadows anywhere. Surfaces separate by value: canvas → card → raised.
- **Touch targets:** at least 44px high.

---

## Logo

Files live in [`assets/logo/`](./assets/logo/). Use the files rather than redrawing.

**Wordmark "Base015."** (the period is part of the logo)
- Inter Tight SemiBold 600, letter-spacing −0.035em, written exactly "Base015." (capital B, the rest lowercase).
- Letters: Ink `#0E0E0E` on light backgrounds, `#F4F4F0` on dark.
- Period: Signal Yellow `#FFCB00` in both modes. This is the one place yellow appears as a glyph, because it is the logo.
- About 18–20px in site and portal headers; body size (16px) in footers; full page width (~19vw) as the closing footer wordmark. Scales freely as a vector.
- `assets/logo/wordmark-on-dark.svg`, `wordmark-on-light.svg`, and `wordmark.svg` (letters use `currentColor`) are outlined from Inter Tight 600 with kerning and the −0.035em tracking applied, so they match the live text.
- As live text: `<span style="font-family:'Inter Tight';font-weight:600;letter-spacing:-0.035em">Base015<span style="color:#FFCB00">.</span></span>`

**App icon / compact mark:** favicon, 512px app icon, Apple touch icon. Use [`assets/logo/app-icon.svg`](./assets/logo/app-icon.svg) as-is; don't redraw it. It's a copy of the portal's `src/app/icon.svg`, served at `https://portal.base015.com/icon.svg`: a 512×512 Ink `#0E0E0E` square with "B." in Inter Tight 600 outlines: a Paper `#FCFCFA` "B" followed by a Signal Yellow `#FFCB00` period on its baseline, a mini version of the wordmark. One dot only.

---

## Components

Every component below is drawn on the reference canvas (Components and Modes boards) in both modes.

- **Primary button:** accent fill, on-accent text, 48–56px high, 32px radius, Inter 500. Hover `--color-accent-hover`, pressed `--color-accent-pressed`, disabled = raised fill with muted text.
- **Ghost button:** transparent, 1px `--color-text` stroke, `--color-text` label, 40px radius.
- **Secondary button:** raised fill, text colour.
- **Text link:** text colour with an underline; hover lowers opacity. Never yellow.
- **Navigation:** sticky bar, canvas at ~86% opacity with backdrop blur, hairline bottom border. Wordmark left, links as 44px pills, the yellow primary pill right. The active item gets a raised fill plus a yellow dot.
- **Inputs:** 48–52px, 32px radius, 1px `--color-border-strong`; labels above in muted text; placeholder in muted text. Email capture: input with a flat right edge joined to a primary button.
- **Tags:** 26–32px pills. Neutral tags use raised; "New" uses an accent fill with Ink text; status tags use a divider stroke plus a yellow dot.
- **Cards:** card fill, 12px radius, 32px padding, no border or shadow. Featured cards may flip to inverse (Ink) with a divider stroke.
- **Tick list:** a 20px yellow disc with an Ink check, then the text.
- **Section header:** a 200px left column with a yellow dot and an uppercase Space Mono label, one word per line; on the right an Inter Tight headline ending in a yellow dot, and a muted lead paragraph.
- **Stat row:** a hairline on top, four columns of Inter Tight values (ending in a yellow dot) over muted labels. Use real, confirmed numbers only.
- **Service tabs:** a column of pill tabs (selected = accent fill, Ink text, mono number) next to a panel with a mono label, heading, body, tick list, optional price note on raised, and an image.
- **Pricing cards:** mono kind label, name, Inter Tight price, one-line description. The featured pack is an inverse card with the yellow primary button.
- **Comparison table:** a "Base015." column with tick discs against a muted alternative column; it scrolls sideways on small screens.
- **Process steps:** a numbered (Space Mono) list; the current or first step has a yellow 2px top rule; deliverable tags on raised.
- **Testimonials:** one yellow proof card (Inter Tight quote in Ink, photo, name, role) plus card-fill quote cards.
- **FAQ accordion:** rows split by dividers; the toggle is a 32–36px circle on raised, which turns into an accent fill with an Ink "−" when open.
- **Call-to-action band:** a full accent band, a huge Inter Tight headline in Ink, Ink dot points, and an Ink button with Ivory text.
- **Footer:** inverse background, link columns with mono headings, the full-width wordmark, then a legal line.
- **Partner logos:** client logos are dark artwork, so in dark mode they sit on Paper tiles (12px radius, 96px high); in light mode, on card tiles.
- **Email (light only):** 600px wide on Paper, a wordmark header, mono eyebrow, Inter Tight heading, a details table on card, one yellow button, and a muted footer with the reason for the email.

---

## Page patterns

The reference marketing page is the sample homepage on the canvas (two boards, because a canvas board is capped at 8,000px).

1. Sticky nav
2. Hero: dot-grid texture, mono eyebrow with a dot, display headline ending in a yellow dot, lead paragraph, primary plus ghost button, and a "Who we work with" card; then a stat row.
3. Media strip of recent shoots on inverse
4. "Trusted by" partner logos on Paper tiles
5. Problem: three numbered cards
6. Services: tabs
7. Pricing: shoot, editing and pack cards, plus a monthly-content row
8. Selected work: case cards with cover image, category tag, headline, summary and one fact with a tick disc
9. Testimonials: a yellow proof card plus two quote cards
10. Comparison table
11. Process: Book → Plan → Shoot → Deliver
12. Founder quote with portrait
13. FAQ accordion
14. Yellow call-to-action band
15. Footer with the giant wordmark

Rules that carry across pages:
- Bands alternate canvas and card.
- Inverse (Ink) is only for media strips and the footer.
- Use the dot-grid texture `radial-gradient(rgba(244,244,240,0.09) 1px, transparent 1.6px)` at 24px in the hero only (dark mode).
- Real content only. Stats stay as visible placeholders until confirmed.

---

## Voice

Direct, plain-spoken, confident and local. Short sentences. No hype words. Say what we do, where, how fast and what it costs. We make ads and content; we don't run or manage ads, so never imply ad management, A/B testing of spend, or "distribution & growth".

---

## Quick start

```css
:root,
[data-theme="light"] {
  --color-canvas: #FCFCFA;
  --color-card: #F3F3EF;
  --color-raised: #E8E8E3;
  --color-divider: #D6D6D0;
  --color-border-strong: #8A8A83;
  --color-text: #0E0E0E;
  --color-text-muted: #55554F;
  --color-focus: #0E0E0E;
}

[data-theme="dark"] {
  --color-canvas: #1C1C1A;
  --color-card: #262624;
  --color-raised: #31312E;
  --color-divider: #6E6E69;
  --color-border-strong: #8F8F8A;
  --color-text: #F4F4F0;
  --color-text-muted: #C2C2BB;
  --color-focus: #F4F4F0;
}

@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --color-canvas: #1C1C1A;
    --color-card: #262624;
    --color-raised: #31312E;
    --color-divider: #6E6E69;
    --color-border-strong: #8F8F8A;
    --color-text: #F4F4F0;
    --color-text-muted: #C2C2BB;
    --color-focus: #F4F4F0;
  }
}

:root {
  /* Same in both modes */
  --color-accent: #FFCB00;
  --color-accent-hover: #FFD633;
  --color-accent-pressed: #E6B700;
  --color-on-accent: #0E0E0E;
  --color-inverse: #0E0E0E;
  --color-ink: #0E0E0E;
  --color-paper: #FCFCFA;
  --color-ivory: #F4F4F0;

  --font-display: 'Inter Tight', 'Inter', system-ui, sans-serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'Space Mono', ui-monospace, monospace;

  --space-4: 4px;  --space-8: 8px;   --space-12: 12px; --space-16: 16px;
  --space-20: 20px; --space-24: 24px; --space-32: 32px; --space-40: 40px;
  --space-56: 56px; --space-72: 72px; --space-112: 112px; --space-128: 128px;

  --radius-structural: 4px;
  --radius-card: 12px;
  --radius-control: 32px;
  --radius-pill: 40px;

  --page-max-width: 1200px;
  --focus-ring: 2px solid var(--color-focus);
  --focus-offset: 3px;
}
```

The marketing site sets `data-theme="dark"` on `<html>`. The portal defaults to light and follows the user's choice. Emails are always light, with inline styles.

### Tailwind v4

Tailwind v4 utilities read the `--color-*` variables at runtime, so declare the light values in `@theme` and override the same variables for dark mode. `bg-canvas`, `text-text-muted` and so on then switch automatically.

```css
@import "tailwindcss";

@theme {
  --color-canvas: #FCFCFA;
  --color-card: #F3F3EF;
  --color-raised: #E8E8E3;
  --color-divider: #D6D6D0;
  --color-border-strong: #8A8A83;
  --color-text: #0E0E0E;
  --color-text-muted: #55554F;
  --color-focus: #0E0E0E;
  --color-accent: #FFCB00;
  --color-accent-hover: #FFD633;
  --color-accent-pressed: #E6B700;
  --color-on-accent: #0E0E0E;
  --color-ink: #0E0E0E;
  --color-paper: #FCFCFA;
  --font-display: 'Inter Tight', 'Inter', system-ui, sans-serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'Space Mono', ui-monospace, monospace;
  --radius-card: 12px;
  --radius-control: 32px;
  --radius-pill: 40px;
}

[data-theme="dark"] {
  --color-canvas: #1C1C1A;
  --color-card: #262624;
  --color-raised: #31312E;
  --color-divider: #6E6E69;
  --color-border-strong: #8F8F8A;
  --color-text: #F4F4F0;
  --color-text-muted: #C2C2BB;
  --color-focus: #F4F4F0;
}
```
