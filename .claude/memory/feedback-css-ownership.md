---
name: feedback-css-ownership
description: User edits CSS independently — never overwrite or re-edit CSS the user has already touched
metadata:
  type: feedback
---

User actively edits the CSS files alongside Claude sessions. Do not re-edit CSS the user has already modified without being explicitly asked.

**Why:** User said "I will be doing updates to the CSS as you go, don't edit my changes." Risk of overwriting in-progress work.

**How to apply:** When touching `.css` files or `<style>` blocks in liquid files, only edit the specific rule asked about. Never do broad reformats or cleanups of CSS the user has authored. If unsure whether a rule is user-authored, ask first.
