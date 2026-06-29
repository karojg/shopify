---
name: project-fgp-overview
description: Feel Good Pharma Shopify store — tech stack, brand tokens, breakpoints, key files
metadata:
  type: project
---

**Project:** Feel Good Pharma (FGP) Shopify store built on the Dawn theme (OS 2.0).

**Brand CSS vars:**
- `--fgp-navy`: #234092
- `--fgp-blue` / `--fgp-picton-blue`: #45bfef
- `--fgp-gold`: #fed304
- `--fgp-white`: #ffffff
- Font: Poppins (`--fgp-font`)

**Breakpoints:**
- Mobile: ≤639px
- Tablet: 640–1023px
- Desktop: ≥1024px

**Key custom files:**
- `snippets/fgp-global.liquid` — global CSS overrides (header icons, cart drawer, nav panel)
- `snippets/fgp-mobile-menu.liquid` — custom hamburger nav drawer (solid navy)
- `sections/fgp-hero-v1.liquid` — homepage hero (navy bg, two-tone heading, bottle image, pill strip)
- `sections/fgp-stressbiotic-feature.liquid` — 3-panel feature section
- `sections/main-login.liquid` — custom login page (white card, a11y)
- `config/settings_data.json` — theme settings
- `layout/theme.liquid` — root layout

**Design source files (local):**
- `figma-design-system.md`
- `design-tokens.md`

**Why Dawn:** Existing store base. FGP overrides Dawn defaults heavily via `!important` due to Dawn's high-specificity selectors — this is expected and intentional.

**How to apply:** When creating new sections, follow the pattern: `{% render 'fgp-global' %}` at top, schema with all content as settings, scoped CSS in a `<style>` block, BEM-like class names prefixed `fgp-`.
