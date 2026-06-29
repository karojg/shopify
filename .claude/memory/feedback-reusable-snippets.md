---
name: feedback-reusable-snippets
description: Build sections as reusable Liquid snippets where possible
metadata:
  type: feedback
---

Prefer building FGP sections as reusable Liquid snippets (`snippets/`) rather than one-off section files.

**Why:** Keeps components DRY and allows them to be included in multiple templates without duplication.

**How to apply:** Global styles and utilities go in `snippets/fgp-global.liquid`. Shared UI patterns (mobile menu, etc.) get their own snippet. Section-specific logic stays in `sections/`.
