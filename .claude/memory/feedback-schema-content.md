---
name: feedback-schema-content
description: All content must come from Shopify section schema settings — never hardcode content
metadata:
  type: feedback
---

All user-facing content (text, images, URLs) must be exposed as Shopify section schema settings, not hardcoded in Liquid templates.

**Why:** Shopify sections need to be editable from the theme customizer. Hardcoded content can't be changed without editing code.

**How to apply:** Any string a merchant might want to change (headings, labels, button text, image sources) goes into `{% schema %}` as a `text`, `image_picker`, or `url` setting and is rendered via `{{ section.settings.* }}`. Exception: structural/decorative strings with no business reason to change.
