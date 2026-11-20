# base015-design

Base015 design system: tokens, fonts, logos and icons shared by the portal and website.

**v3: cinematic and dark-led, one yellow signal.** It comes from the website redesign and replaces v2 ("Editorial paper").

- [`DESIGN.md`](./DESIGN.md): the spec. Colour, type, layout, components, motion and video, copy rules.
- [`tokens/base015.css`](./tokens/base015.css): the tokens and a small set of base classes.
- [`assets/logo/`](./assets/logo/): the wordmark and app icon.
- [`CLAUDE.md`](./CLAUDE.md): the short version, for Claude.

## What changed from v2

| | v2 | v3 |
|---|---|---|
| Canvas | Paper, with Ink bands | Ink, with Paper sections (`.surface-paper`) |
| Headings | Instrument Serif 400 | Archivo 600–800 with the width axis |
| Labels | Space Mono, uppercase, with a dot | Inter 15px, normal case; no overline labels |
| Numbers | Inter Tight 560 | Archivo 800, width 115, tabular |
| Yellow | Pills, an editorial card, a wash, dots after headlines | The main button, focus on dark, active states, live dots |
| Focus ring | Text colour | Yellow on dark, Ink on Paper |
| Radius | 24px cards, 12px media | 20px cards, 16px media |
| Container | 1200px, 80px sections | 1360px, 12 columns, 120px sections |
| Hero | Floating UI artifacts with a shadow | Real vertical ads playing |
| Smallest text | 12px | 14px |
| Website default | no attribute = light | no attribute = Ink |
| Portal | no attribute = light, `data-theme="dark"` | `data-theme="light"` or `data-theme="dark"`, always set |

Token names are the same as v2, so components keep their utilities. Removed: `--shadow-artifact`, `--radius-artifact`, the `.artifact`, `.card-editorial`, `.chip-wash` and `.dot-end` classes. `--color-accent-wash` and `--font-mono` still resolve, to neutrals.
