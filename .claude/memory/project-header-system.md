---
name: project-header-system
description: FGP unified header UI system — nav drawer, cart drawer, icons all navy
metadata:
  type: project
---

All three header components use the same navy system:

**Nav drawer** (`snippets/fgp-mobile-menu.liquid`):
- Background: `var(--fgp-navy, #234092)` solid (no frosted glass)
- Logo at top (white/inverted), close button (X SVG), nav links below
- Link dividers: `rgba(255,255,255,0.18)`

**Cart drawer** (overrides in `snippets/fgp-global.liquid`):
- Background: `var(--fgp-navy)` with `!important`
- Text: white; prices: gold (`var(--fgp-gold)`); checkout button: gold
- Continue shopping: white outline pill
- Login link: `var(--fgp-blue, #45bfef)` with underline

**Header icons** (overrides in `snippets/fgp-global.liquid`):
- All icons white globally (hamburger, cart, account)
- Applied without media query so it covers desktop too

**Why:** User requested consistent navy system across all header UI after cart was transparent and icons were inconsistent colors.

**How to apply:** Any new header UI element should default to this navy/white/gold palette.
