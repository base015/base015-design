# Base015 — Design System v2
> Editorial paper, one yellow signal

Base015 makes video ads and monthly content for service businesses in Sacramento, Roseville and Folsom. The system is light-first and editorial: a paper canvas, serif headlines at regular weight, flat 24px cards, pill controls in filled + ghost pairs, and colour rationed to the one thing to do next. **Signal Yellow** (`#FFCB00`) is the only accent and it is always a **fill with Ink text**: never text, icons, outlines or focus rings.

v2 is inspired by two references: Steep (serif editorial on white paper, floating product cards, one rare accent card) and VEED (a video tool: a single accent for the main action, full-bleed dark bands, portrait media cards). Everything that is Base015 stays: the wordmark and app icon, Signal Yellow with Ink on it, the yellow dot, the voice, the real prices.

| Surface | Mode |
|---------|------|
| Marketing website | **Light** (Paper & Ink). Ink bands for rhythm. |
| Client portal | **Light-first**, with the charcoal **dark** mode as the user's choice |
| Emails, documents | Light only |

Shared tokens for the website and portal: [`tokens/base015.css`](./tokens/base015.css).

---

## Colour

Semantic tokens; components never hard-code a mode.

| Token | Role | Light | Dark |
|-------|------|-------|------|
| `--color-canvas` | Page background | `#FCFCFA` Paper | `#1C1C1A` Soft charcoal |
| `--color-card` | Content cards, input fills, nested blocks | `#F3F3EF` Mist | `#262624` |
| `--color-band` | Alternating section bands, hover surfaces | `#F8F8F5` Fog | `#222220` |
| `--color-raised` | Secondary buttons, chips, progress tracks | `#E8E8E3` | `#31312E` |
| `--color-hairline` | Card and input borders, dividers | `#E6E6E2` | `#3A3A37` |
| `--color-rule` | Table rules, stronger separators | `#D6D6D0` | `#6E6E69` |
| `--color-text` | Primary text, ghost-button stroke, focus ring | `#0E0E0E` Ink | `#F4F4F0` Ivory |
| `--color-text-muted` | Leads, helper text, footer copy | `#55554F` | `#C2C2BB` |
| `--color-text-smoke` | Placeholders, disabled labels, typographic tags | `#8A8A83` | `#8F8F8A` |
| `--color-accent` | Signal Yellow — fills only | `#FFCB00` | `#FFCB00` |
| `--color-accent-hover` | Primary pill hover | `#FFD633` | `#FFD633` |
| `--color-accent-pressed` | Primary pill pressed | `#E6B700` | `#E6B700` |
| `--color-accent-wash` | Soft emphasis behind text and badges, Ink on top | `#FFF3C4` | `#3D3410` |
| `--color-on-accent` | Text and icons on any yellow fill | `#0E0E0E` | `#0E0E0E` |
| `--color-inverse` | Dark bands, footer, featured card | `#0E0E0E` | `#0E0E0E` |
| `--color-on-inverse` | Text on inverse | `#F4F4F0` | `#F4F4F0` |

Brand constants: Ink `#0E0E0E`, Paper `#FCFCFA`, Ivory `#F4F4F0`, Signal Yellow `#FFCB00`.

**Status colours (portal only).** A portal needs success, warning and danger. They are muted so they never compete with yellow, and they are never used for marketing emphasis: success `#1E6B45` / soft `#E7F3EC`, warning `#8A5A00` / soft `#FDF3DC`, danger `#A3261D` / soft `#FBECEB`. Dark values are in `tokens/base015.css`.

Contrast: text on canvas, card and band passes AA in both modes (muted ≥6:1). Ink on yellow is 12.7:1; white on yellow is 1.5:1 and never used. Smoke `#8A8A83` is for placeholders and tags only, never for sentences.

### Signal Yellow rules

1. **Fill only, Ink on top.** The primary pill, the one editorial card, the selected tab, the open accordion icon, the brief composer's send disc, play discs on media, tick discs, progress fills, the small dot.
2. **One yellow pill per view.** Every filled pill is paired with a ghost pill on the same row.
3. **One yellow editorial card per page**, for the proof moment, on Paper or Mist, never on a dark band. It is the only chromatic surface on the page (Steep's accent-card role).
4. **The wash is for emphasis, never for action**: a highlighted phrase, a trust badge, a note. Ink text on it.
5. **The dot is the motif.** A 6px yellow dot sits before section labels and marks active, new or live items. Display headlines end in a filled yellow dot (~0.14em), echoing the logo's period. Never rely on the dot alone for state: pair it with a raised fill or a label.
6. No second hue on marketing surfaces. Status colours exist only in the portal.

---

## Typography

Four families, all free (SIL OFL), loaded from Google Fonts. No font files are committed.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Inter+Tight:wght@100..900&family=Instrument+Serif:ital@0;1&family=Space+Mono:wght@400;700&display=swap">
```

| Family | Token | Use |
|--------|-------|-----|
| **Instrument Serif** | `--font-display` | H1 and H2 only, 40px and up. Regular weight (400) at every size, never bold. One italic phrase per headline is allowed. Tracking −0.02em at 88px+, −0.015em at 44–64px; line-height 0.98–1.1. Never below 40px and never in UI. |
| **Inter** | `--font-body` | Body, UI, buttons, inputs, tables, H3. 17px / 1.5 on the website, 16px in the portal. 400 body, 450 leads, 500 buttons, nav and H3. |
| **Inter Tight** | `--font-numbers` | Prices, stats and the wordmark: 560 for numbers, 600 for the logo, tracking −0.02em. |
| **Space Mono** | `--font-mono` | Uppercase 12px labels, step numbers, metadata, +0.04em. Never sentences. |

### Type scale

| Role | Family | Size / line-height | Weight | Tracking |
|------|--------|--------------------|--------|----------|
| Display | Instrument Serif | 88–96px / 0.98 (clamp on pages) | 400 | −0.02em |
| Heading lg | Instrument Serif | 64px / 1.02 | 400 | −0.015em |
| Heading | Instrument Serif | 44px / 1.1 | 400 | −0.015em |
| Heading sm | Inter | 24–26px / 1.2 | 500 | −0.01em |
| Subheading | Inter | 22px / 1.5 | 400 | 0 |
| Lead | Inter | 18–20px / 1.4 | 450 | 0 |
| Body | Inter | 17px / 1.5 (portal 16px) | 400 | 0 |
| Caption | Inter | 14–15px / 1.5 | 400 | 0 |
| Label | Space Mono | 12px / 1.3, uppercase | 400 | +0.04em |
| Price / stat | Inter Tight | 30–56px / 1 | 560 | −0.02em |

---

## Space, shape, elevation

- **Spacing:** 4px base. 4, 8, 12, 16, 20, 24, 28, 32, 40, 48, 64, 80, 96, 112.
- **Layout:** 1200px max width, 24px gutters. Section padding 80px (96px for Ink bands, 112px for the closing call to action). Card padding 28–32px, dense cards 20px. Element gap 8–12px.
- **Radius:** `--radius-pill` 9999px for buttons, chips and tabs; `--radius-card` 24px for content cards; `--radius-small` 16px for inputs, small cards and the composer; `--radius-media` 12px for images and video stills; 20px for floating artifacts; 50% for dots, discs and avatars. Nothing under 12px on the website; the portal may use 8px for dense table chrome.
- **Elevation:** flat. Surfaces separate by value (canvas → card → raised) and hairlines. **One exception:** the floating artifacts around the hero carry `--shadow-artifact`: `0 0 0 1px rgba(14,14,14,.06), 0 20px 25px -5px rgba(14,14,14,.10), 0 8px 10px -6px rgba(14,14,14,.10)`. Dialogs and menus in the portal use `--shadow-overlay`. Content cards never have a shadow.
- **Touch targets:** 44px or more. Focus ring: 2px solid `--color-text`, offset 3px.

---

## Logo

Files are in [`assets/logo/`](./assets/logo/). Use them rather than redrawing.

- **Wordmark "Base015."** (the period is part of the logo). Inter Tight 600, letter-spacing −0.035em; letters Ink on light, Ivory on dark; the period Signal Yellow in both. The outlined SVGs (`wordmark-on-light.svg`, `wordmark-on-dark.svg`, `wordmark.svg` with `currentColor` letters) match the live text exactly. As live text: `<span style="font-family:'Inter Tight';font-weight:600;letter-spacing:-0.035em">Base015<span style="color:#FFCB00">.</span></span>`. 18–20px in headers, 16px in footers, full page width (~19vw) as the closing footer wordmark.
- **App icon:** `assets/logo/app-icon.svg`, a copy of the portal's `src/app/icon.svg`. Use as-is.

The logo keeps Inter Tight; headlines are the serif. That contrast (sans wordmark, serif headlines) is intended, as in VEED.

---

## Components

All are drawn on the reference canvas (System page).

- **Primary pill:** accent fill, on-accent text, Inter 500, 44–52px high, `--radius-pill`. Hover `--color-accent-hover`, pressed `--color-accent-pressed`, disabled raised fill with smoke text. One per view.
- **Ghost pill:** transparent, 1px `--color-text` stroke and label. The partner of every primary pill. On Ink bands the stroke and label are Ivory.
- **Ink pill:** inverse fill, Ivory text. Portal sign-in and secondary conversion.
- **Text link:** text colour, an arrow suffix, underline on hover only.
- **Navigation:** no background, no border, no shadow (Steep). Wordmark left, 44px text links centre, a "Client portal" text link and the primary pill right. The active item carries the yellow dot. On scroll it may gain a Paper fill at 90% with a hairline.
- **Floating artifacts:** 20px radius, Paper, `--shadow-artifact`, 200–360px wide, rotated ±1.5–3°, placed around the hero headline. The set for a video studio: a portrait reel still with a yellow play disc and a category chip; the booking card (shoot-length chips, a day picker, "Finished ads within 7 days"); a price stat with a gestural line; the brief composer. Nowhere else on the page has a shadow.
- **Composer:** 16px radius, hairline, a one-line prompt ("Tell us what you need filmed…"), service chips, and a 40px yellow send disc. It leads to booking; it is not a chat.
- **Inputs:** 52px, 16px radius, 1px hairline, label above in muted, placeholder in smoke. Card fill when inside a card.
- **Cards:** Mist, 24px radius, 28–32px padding, no border or shadow. Sections alternate Paper and Fog bands. Featured card: inverse with the primary pill. Editorial card: accent fill, a serif quote in Ink, photo, name, role.
- **Tags:** typographic, in smoke, no background (Steep). Status chips: the wash with Ink text, or a hairline chip with the yellow dot. Media chips: 12px white text on `rgba(14,14,14,.55)`, 6px radius, top-left of a still.
- **Reel cards:** portrait 220×340, 12px radius, full-bleed still, category chip top-left, a 36px yellow play disc bottom-right; a horizontal row with 16px gaps and dot pagination (active 10px Ink, inactive 8px hairline).
- **Dark band:** full-bleed inverse, 96px padding, a serif headline in Ivory, VEED's asymmetric 60/40 media grid at 16px radius with captions over the stills. The yellow play disc is the only colour on the band.
- **Section header:** a 200px mono label column with the yellow dot (one word per line), then a serif headline ending in a yellow dot and a lead in muted.
- **Accordion:** hairline rows, 68px, a 36px disc (hairline fill, Ink "+") that becomes accent with an Ink "−" when open.
- **Process steps:** four Paper cards on a Fog band, mono step labels with the dot (yellow on the current step), H3, body, typographic tags.
- **Closing call to action:** quiet, on Paper: a serif headline, a lead, the pill pair. Not a yellow band; the editorial card already spent the page's yellow surface.
- **Footer:** inverse, link columns with mono headings, the full-width wordmark, a legal line.
- **Portal frames:** the same tokens and radii at 16px body. Tables keep 1px rules; dialogs and menus use `--shadow-overlay` on Paper; the drawer scrim is `rgb(0 0 0 / .6)`. Status colours as listed above.

---

## Page pattern (marketing homepage)

1. Nav
2. Hero: a wash badge (service area), a centred serif display headline with one italic phrase and the yellow dot, a lead, the pill pair; four floating artifacts around it
3. Partner logo row (monochrome logos on Paper, no tiles)
4. Services: three Mist cards on a Fog band
5. Pricing: Mist price cards, the inverse Ad Pack card, a wash row for Monthly Content
6. Ink work band: serif headline, 60/40 media grid of case studies, a ghost pill
7. Testimonials: the one yellow editorial card plus two Mist quote cards
8. Process on a Fog band
9. Founder quote in the serif with portrait
10. FAQ accordion on a Fog band
11. Closing call to action with the pill pair
12. Footer with the giant wordmark

Real content only. Stats stay as visible placeholders until confirmed.

---

## Voice

Direct, plain-spoken, confident and local. Short sentences. No hype words. Say what we do, where, how fast and what it costs. We make ads and content; we don't run or manage ads, so never imply ad management, A/B testing of spend, or "distribution & growth".

---

## Quick start

Load [`tokens/base015.css`](./tokens/base015.css) and the fonts link above. The website sets nothing (light is the default); the portal sets `data-theme="dark"` on `<html>` when the user chooses it. Emails inline the light values.

```html
<link rel="stylesheet" href="tokens/base015.css">
<button class="btn btn-primary">Book a shoot</button>
<button class="btn btn-ghost">See the work</button>
```

### Tailwind v4

```css
@import "tailwindcss";
@import "./tokens/base015.css";

@theme inline {
  --color-canvas: var(--color-canvas);
  --color-card: var(--color-card);
  --color-band: var(--color-band);
  --color-raised: var(--color-raised);
  --color-hairline: var(--color-hairline);
  --color-rule: var(--color-rule);
  --color-text: var(--color-text);
  --color-text-muted: var(--color-text-muted);
  --color-text-smoke: var(--color-text-smoke);
  --color-accent: var(--color-accent);
  --color-accent-wash: var(--color-accent-wash);
  --color-on-accent: var(--color-on-accent);
  --color-inverse: var(--color-inverse);
  --color-on-inverse: var(--color-on-inverse);
  --font-display: var(--font-display);
  --font-body: var(--font-body);
  --font-mono: var(--font-mono);
  --radius-pill: var(--radius-pill);
  --radius-card: var(--radius-card);
  --radius-small: var(--radius-small);
  --radius-media: var(--radius-media);
}
```

`@theme inline` keeps the utilities pointing at the variables, so `bg-canvas` and `text-text-muted` switch with `data-theme` automatically.
