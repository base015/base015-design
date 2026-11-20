# Base015 — Design System v3
> Cinematic and dark-led, one yellow signal

Base015 makes video ads and monthly content for service businesses in Sacramento, Roseville and Folsom. The system is dark-led and video-first: an Ink canvas, real footage, heavy wide grotesk headlines, flat 20px cards, fully rounded buttons and a strict 12-column grid. **Signal Yellow** (`#FFCB00`) is the only accent and it is a **signal**: the main button, focus on dark, active states and small live dots. Always a fill with Ink on it, never text and never a large area.

v3 comes from the website redesign (`base015-website`, branch `redesign`, `docs/redesign/BRIEF.md`) and replaces v2 ("Editorial paper"). The wordmark, the app icon, the four brand colours and the voice carry over. References: Partizan, 1820 Productions, Umault, Hatom, Lusion.

| Surface | Mode |
|---------|------|
| Marketing website | **Ink** by default. Paper sections for rhythm. |
| Client portal | `data-theme="light"` (Paper) or `data-theme="dark"` (charcoal), the user's choice. v3 type, shape and yellow rules. |
| Slides, social, OG images | Ink |
| Emails, documents | Paper (dark backgrounds are unreliable in mail and print). v3 type and rules. |

Shared tokens for the website and portal: [`tokens/base015.css`](./tokens/base015.css).

---

## What v3 removed

These read as a template. None of them comes back.

- Serif headlines, a half-italic phrase, a yellow dot or full stop after a heading. The yellow period lives in the logo only.
- Eyebrow or overline labels above headings, uppercase mono labels, a dot before a label.
- Fake UI widgets floating around a hero (booking card, price card, chat composer), and the shadow under them.
- Three equal numbered cards (01 / 02 / 03).
- Large yellow surfaces: the yellow editorial card and the pale-yellow wash.
- Middle-dot separators between bits of text ("Half day · $600"). Use icons or separate lines.
- Text under 14px.
- Text links as main actions.
- Drop shadows under mockups, chrome, bevel, embossing, clipart-style vectors.
- Sections made of paragraphs.

---

## Colour

Semantic tokens; components never hard-code a surface. A section switches surface with a class, and everything inside follows.

| Token | Role | Ink (default, `.surface-inverse`) | Paper (`.surface-paper`) |
|-------|------|-----------------------------------|--------------------------|
| `--color-canvas` | Section background | `#0E0E0E` Ink | `#FCFCFA` Paper |
| `--color-card` / `--color-band` | Cards, input fills | `#161615` | `#F3F3EF` Mist |
| `--color-raised` | Icon squares, badges, tile placeholders, disabled fills | `#1F1F1D` | `#E8E8E3` |
| `--color-hairline` | Dividers, card and input borders | white at 8% | Ink at 8% |
| `--color-rule` | Stronger separators, chip outlines, input hover | white at 16% | Ink at 16% |
| `--color-text` | Primary text | `#F4F4F0` Ivory | `#0E0E0E` Ink |
| `--color-text-muted` | Leads, helper text, footer copy | Ivory at 64% | `#55554F` |
| `--color-text-smoke` | Placeholders, disabled labels, faint text | Ivory at 52% | `#6E6E68` |
| `--color-focus` | Focus ring | `#FFCB00` | `#0E0E0E` |
| `--color-accent` | Signal Yellow, fills only | `#FFCB00` | `#FFCB00` |
| `--color-accent-hover` / `-pressed` | Primary pill states | `#FFD633` / `#E6B700` | same |
| `--color-on-accent` | Text and icons on yellow | `#0E0E0E` | `#0E0E0E` |

Brand constants: Ink `#0E0E0E`, Paper `#FCFCFA`, Ivory `#F4F4F0`, Signal Yellow `#FFCB00`.

`--color-accent-wash` is retired. The token still resolves, to the raised neutral, so old call sites don't break.

**Portal themes.** The portal sets `data-theme` on `<html>`. Light is the Paper column above with Fog `#F8F8F5` as its band. Dark is the softer charcoal, kinder over a long session than pure Ink: canvas `#1C1C1A`, card `#262624`, band `#222220`, raised `#31312E`, hairline `#3A3A37`, rule `#6E6E69`, text Ivory, muted `#C2C2BB`, smoke `#8F8F8A`, focus yellow.

**Status colours (portal only).** Muted, so they never compete with yellow, and never used for marketing emphasis: success `#1E6B45` / soft `#E7F3EC`, warning `#8A5A00` / soft `#FDF3DC`, danger `#A3261D` / soft `#FBECEB` on light. Dark values are in `tokens/base015.css`.

Contrast: every text token passes AA on its canvas and card. On Ink, muted is 7.5:1 and smoke 5.3:1. On Paper, muted is 7.3:1 and smoke 5.0:1 (4.6:1 on Mist). Ink on yellow is 12.7:1. Yellow on Paper is 1.5:1, which is why yellow is never text and never the focus ring on a light surface.

### Signal Yellow rules

1. **A signal, not a surface.** The main button, the focus ring on dark surfaces, an active state (the current step's bar, a progress fill), the 6px dot on the current nav item, the 8px live dot. Nothing bigger than a button.
2. **Fill only, Ink on top.** Never yellow text, icons or outlines. Never yellow text on white.
3. **One yellow button in view.** Where a section has one action, that action is the yellow one. Its partner is the outline pill. A persistent yellow button (the header pill) fades while a section's own yellow button is on screen.
4. **Sticky bars and menus carry no yellow.** There the main action is a solid pill in the text colour and the second an outline.
5. **Never rely on the dot alone for state.** Pair it with weight, a label or `aria-current`.
6. No second hue on marketing surfaces. Icons are white on Ink and Ink on Paper. Review stars are the text colour. Status colours exist only in the portal.

---

## Typography

Two families, both free (SIL OFL), loaded from Google Fonts. No font files are committed.

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@100..125,600..800&family=Inter:wght@400..600&display=swap">
```

In Next.js use `next/font/google` with `Archivo({ axes: ["wdth"] })` and `Inter`, so the files are served from the site itself. Preload Archivo only: the H1 is usually the largest paint.

| Family | Token | Use |
|--------|-------|-----|
| **Archivo** | `--font-display`, `--font-numbers` | Headings, prices and big numbers. Heavy and wide at the top, calmer below: it uses the width axis. |
| **Inter** | `--font-body` | Everything else: body, leads, buttons, inputs, tables, labels, quotes. |

Space Mono, Instrument Serif and Inter Tight as a text face are retired. `--font-mono` still resolves, to Inter.

### Type scale

| Role | Family | Size / line-height | Weight, width | Tracking |
|------|--------|--------------------|---------------|----------|
| H1 | Archivo | `clamp(48px, 5.6vw, 88px)` / 0.95 | 800, width 115 | −0.035em |
| Homepage H1 | Archivo | `clamp(56px, 5.6vw, 84px)` / 0.95 from 1024px | 800, width 115 | −0.035em |
| H2 | Archivo | `clamp(40px, 4.6vw, 72px)` / 1 | 700, width 112 | −0.03em |
| H3 | Archivo | 24–28px / 1.15 | 600, width 100 | −0.01em |
| Price / big number | Archivo | 34px in cards, up to 152px on case cards / 0.9–1 | 800, width 115, tabular figures | −0.02em |
| Pull quote | Inter | 26–44px / 1.2–1.25 | 500 | −0.015em |
| Lead | Inter | 18–20px / 1.55, muted, max 46ch | 400 | 0 |
| Body | Inter | 17px, 18px from 1024px / 1.55 (portal 16px), max 60ch | 400 | 0 |
| Label | Inter | 15px / 1.4, normal case | 500 | 0 |
| Small | Inter | 14px minimum | 400 | 0 |
| Button | Inter | 16px (15px small) | 600 | 0 |

Rules:

- Headings use `text-wrap: balance`, no trailing full stop, no italic, no decoration.
- **Nothing in the UI under 14px.**
- Left-aligned. No centred paragraphs. A centred one-line heading is fine in a closing call to action.
- Set width with both `font-stretch` and `font-variation-settings: "wdth"`, as the tokens file does.

---

## Space, shape, elevation

- **Grid:** 1360px container, 24px sides (16px on phones). 12 columns with 24px gutters; 4 columns with 16px gutters on phones. Every section sits on it, tidy and aligned.
- **Section rhythm:** 120px between sections (72px on phones). 24px from heading to lead, 56–64px from the section header to its content.
- **Spacing:** 4px base. 4, 8, 12, 16, 20, 24, 32, 40, 48, 56, 64, 72, 96, 120.
- **Radius:** `--radius-pill` 9999px for buttons, chips and badges; `--radius-card` 20px; `--radius-small` 16px for inputs and small cards; `--radius-media` 16px for stills and video tiles (small tiles scale down to about 10px); icon squares 9px at 32px and 7px at 24px; 50% for dots and avatars. The portal may use 8px for dense table chrome.
- **Dividers:** 1px at 8% of the text colour, 16% where a stronger rule is needed.
- **Elevation:** flat. Surfaces separate by value (canvas → card → raised) and hairlines. No shadows on the website at all. Dialogs and menus in the portal use `--shadow-overlay`. A sticky header or bar uses Ink at 85–90% with a 16px backdrop blur and a hairline, not a shadow.
- **Touch targets:** 44px or more. Focus ring: 2px solid `--color-focus`, offset 3px.

---

## Logo

Files are in [`assets/logo/`](./assets/logo/). Use them rather than redrawing. The wordmark is unchanged from v2.

- **Wordmark "Base015."** (the period is part of the logo, and the one yellow glyph allowed). Use the outlined SVGs: `wordmark-on-dark.svg` on Ink, `wordmark-on-light.svg` on Paper, `wordmark.svg` with `currentColor` letters. 16–20px tall in headers and footers, full container width as the closing footer wordmark.
- **As live text**, only where an SVG can't go: Inter Tight 600, letter-spacing −0.035em, Ivory on dark or Ink on light, then a "." in Signal Yellow. Load Inter Tight for this alone.
- **App icon:** `assets/logo/app-icon.svg`. Use as-is.

---

## Icons

- 16px line glyphs on a 16-unit grid, 1.5 stroke, round caps and joins, `currentColor`.
- They sit in a rounded square filled with the block's raised colour (`.icon-tile`): 32px with a 9px radius, or 24px with 7px. White on Ink, Ink on Paper. Never yellow.
- Ticks in lists use the same square. Icons replace middle dots wherever facts sit side by side (price, time, place).

---

## Components

- **Primary pill:** accent fill, Ink text, Inter 600, 52px high (44px small), fully rounded. Hover `--color-accent-hover`, pressed `--color-accent-pressed`, disabled raised fill with smoke text. One in view. May carry a 16px arrow that slides 2px on hover.
- **Outline pill:** transparent, a 1px border in the text colour at 24%. On hover it fills with the text colour and the label takes the canvas colour. The partner of the primary pill.
- **Solid pill:** a fill in the text colour (white on Ink, Ink on Paper). The main action wherever yellow isn't allowed: the mobile bar, the mobile menu.
- **Text link:** text colour, underline on hover only, optional arrow suffix. Inside running text the underline stays. Never the main action of a section.
- **Header:** sticky, 72px (64px on phones), transparent at the top so a hero can run under it. After 8px of scroll: Ink at 85%, a 16px backdrop blur and an 8% hairline. Wordmark left, 44px text links in muted at 15px, the current one in the text colour at 500 with the 6px yellow dot, a quiet "Log in" link and the small primary pill right.
- **Mobile menu:** a full-screen Ink overlay under the header bar. Links in Archivo 600 at 32–42px, then both actions (solid pill, outline pill), phone, email and the portal login. Focus stays inside; Escape closes it.
- **Mobile bottom bar:** appears once the hero has scrolled past. Ink at 90% with blur and a top hairline; a solid pill and an outline pill, no yellow. The header pill hides while it shows. Not on pages with a form.
- **Section header:** from 1024px the H2 spans 8 columns on the left and the lead the last 4, aligned to the H2's last baseline. Below that the lead sits 24px under the H2. No label above it. Many sections need no lead.
- **Cards:** `--color-card`, 20px radius, 32px padding, no border, no shadow. An Ink card may sit in a Paper section (`.surface-inverse`).
- **Video tile:** 9:16, 16px radius. The poster shows from the start and the video fades in only after its first frame. A silent loop while in view; tap for sound. Client and trade as text under the tile, not a chip over it.
- **Feed strip:** a horizontal, draggable row of video tiles that bleeds off the right edge. The first tile lines up with the container and tiles snap to that line. Arrow buttons and tab stops for the keyboard.
- **Case card:** a full-bleed cover with a bottom gradient (black 72% → 0), the production fact as the biggest thing on the card (`.num`, 64–152px), the client and trade under it. On hover the cover zooms to 1.04 over 1.2s and a 104px Ivory "View case" disc follows the pointer; on phones a 40px outlined arrow disc sits bottom-right.
- **Logo band:** client logos in one colour, white at 70% on Ink (Ink at 80% on Paper), full strength on hover. A slow marquee with faded edges that pauses on hover and focus.
- **Reviews:** on Paper. One quote large (Inter 500, up to 44px, 22ch) and the rest as cards. Each review shows its own five stars in the text colour. No aggregate rating or count unless confirmed.
- **Price table:** rows with hairlines, the name left and the price in `.num` right. Facts beside a price get icons, not dots.
- **Tier cards:** selecting a tier lights its share of a wall of video tiles; the others dim to 25%.
- **Process:** a sticky list of step names (Archivo 600, 32–40px) beside tall panels. The active step is full strength with its line open and a 2px yellow progress line; the others sit at 40%. Without motion every step is open.
- **Trade rows:** large rows (Archivo 700, 34–56px) divided by hairlines. On hover the name shifts 12px right and a poster follows the pointer.
- **Accordion:** native `<details>` rows with hairlines, 76px minimum, the question at 18px / 500, and a 36px raised square (10px radius) with a plus that turns into a minus. One open at a time. The answer is muted, max 60ch.
- **Inputs:** 52px, 16px radius, card fill, hairline border, the label above at 15px in muted, the placeholder in smoke. Hover: the rule colour. Focus: a border and 1px ring in `--color-focus`, replacing the offset outline. Invalid: a 2px border in the text colour with an icon and message under it. No red on the website.
- **Step indicator:** steps side by side, each with a 2px top border: yellow for the current one, rule with a tick for a finished one, hairline and smoke for the next.
- **Tags and chips:** a tag is 14px muted text with no background. A status chip is a 32px pill with a 1px rule outline. A badge is a 36px pill on the raised fill.
- **Live dot:** 8px, yellow, with a slow pulse that stops under reduced motion.
- **Closing call to action:** Ink. One big statement, both pills, phone and email on separate lines. Behind it, a wall of posters at 15% opacity, blurred and drifting slowly.
- **Footer:** Ink. The wordmark and one line, link columns on the 12-column grid with 15px muted titles, the full-width wordmark, then a legal line over a hairline with the portal login.
- **Portal frames:** the same tokens, type and radii at 16px body. Tables keep 1px rules; dialogs and menus use `--shadow-overlay`; the drawer scrim is `rgb(0 0 0 / .6)`. Status colours as listed above.

---

## Motion and video

The site behaves like the product: vertical 9:16 ads play across it. Everything else stays calm.

- **At most three big moments per page.** On the homepage: the hero's wall of ads that settles into a centred phone on scroll, the Trust Engine's curved wall of tiles, and work cards that respond to the pointer. The rest is a restrained reveal.
- **Reveal:** 16px rise and fade, 600ms, `cubic-bezier(0.2, 0.7, 0.2, 1)` (`--ease-out`). Hover and colour changes 150ms; state changes 200–400ms.
- **Motion needs permission.** Scroll pinning, drifting walls and reveals run only without `prefers-reduced-motion` and without Save-Data. Otherwise: posters, no pinning, every step open, marquees still and scrollable by hand.
- **Video:** `preload="none"`, muted and inline, with the poster as an image under it. A tile is never black: before the poster arrives it shows a blurred preview or the poster's average colour.
- **One playback limit per page:** at most 5 videos playing on wide screens and 3 below 1024px, the most visible first. The rest show posters.
- Heavy libraries (GSAP, anything 3D) load on demand, after motion is allowed.

---

## Page pattern (marketing homepage)

Ink and Paper alternate for rhythm. Every strong section ends in an action: Book a strategy call or Book a shoot.

| # | Section | Surface | Action |
|---|---------|---------|--------|
| 1 | Hero: H1, lead, both pills, a proof line with icons, the wall of ads | Ink | Book a strategy call (yellow), Book a shoot |
| 2 | Logo marquee | Ink | none |
| 3 | The feed: a strip of vertical ads | Ink | See all work |
| 4 | Two ways to work: two large cards with media, a price and an icon list | Paper | one per card |
| 5 | Selected work: case cards led by a production number | Ink | All work |
| 6 | Reviews | Paper | Book a shoot |
| 7 | Monthly plan: the video wall and tiers | Ink | Book a strategy call |
| 8 | Pricing table | Paper | Book a shoot |
| 9 | Process | Ink | none |
| 10 | Founder: portrait and quote | Ink | Book a strategy call |
| 11 | Trades rows | Paper | each row links to its page |
| 12 | FAQ accordion | Paper | none |
| 13 | Closing call to action | Ink | both pills, phone, email |
| | Footer with the giant wordmark | Ink | |

Sections are built from video, photos, numbers and interaction, not paragraphs. Real content only. Unconfirmed numbers stay as visible placeholders.

---

## Copy and text layout

- **Headings and leads:** every section gets a heading and at most one short lead (20 words or fewer). No lead that restates the heading.
- **Paragraphs:** on a homepage, at most two short sentences. Detail lives on inner pages, in accordions or behind a link.
- **Numbers beat sentences:** a big number with a short label, then one line. Numbers are production facts ("9 ads in one shoot day") or a result a client said themselves, attributed.
- **Lists:** at most six items, two to five words each, with an icon.
- **Words:** plain words a contractor would say. Specific facts over adjectives.
- **Never:** generic headings ("What our clients are saying", "Why choose us"), a colon followed by a list, semicolon pairs, groups of three for rhythm, "not just X, but Y", "Whether you're… or…", rhetorical questions, exclamation marks, em-dash asides, or words like seamless, elevate, unlock, empower, crafted, tailored, journey, world-class, solutions.

## Voice

Direct, plain-spoken, confident and local. Short sentences. No hype words. Say what we do, where, how fast and what it costs. We make the ads. Clients run them. Never imply ad management, A/B testing of spend, or promised ad results.

---

## Quick start

Load [`tokens/base015.css`](./tokens/base015.css) and the fonts link above. The website sets nothing (Ink is the default) and wraps light sections in `.surface-paper`. The portal sets `data-theme="light"` or `data-theme="dark"` on `<html>`. Emails inline the Paper values.

```html
<link rel="stylesheet" href="tokens/base015.css">

<section class="band">
  <div class="page-x">
    <h2>Nine ads from one shoot day</h2>
    <a class="btn btn-primary" href="/strategy-call">Book a strategy call</a>
    <a class="btn btn-ghost" href="https://portal.base015.com/book">Book a shoot</a>
  </div>
</section>

<section class="band surface-paper">…</section>
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
  --color-focus: var(--color-focus);
  --color-accent: var(--color-accent);
  --color-accent-hover: var(--color-accent-hover);
  --color-accent-pressed: var(--color-accent-pressed);
  --color-on-accent: var(--color-on-accent);
  --color-inverse: var(--color-inverse);
  --color-on-inverse: var(--color-on-inverse);
  --color-ink: var(--color-ink);
  --color-paper: var(--color-paper);
  --color-ivory: var(--color-ivory);
  --font-display: var(--font-display);
  --font-sans: var(--font-body);
  --font-numbers: var(--font-numbers);
  --radius-pill: var(--radius-pill);
  --radius-card: var(--radius-card);
  --radius-small: var(--radius-small);
  --radius-media: var(--radius-media);
}
```

`@theme inline` keeps the utilities pointing at the variables, so `bg-canvas` and `text-text-muted` follow `.surface-paper`, `.surface-inverse` and `data-theme` automatically.
