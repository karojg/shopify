# Translations — EN / ES

The site targets **English** and **Spanish** only. Text on this theme lives in three
separate layers, and only two of them are controlled by files in this repo.

| Layer | Where it lives | Locale-aware? | Status |
|---|---|---|---|
| 1. Theme strings | `locales/en.default.json`, `locales/es.json` | Yes — via `\| t` | **Done** |
| 2. Schema `default` values | `{% schema %}` in each section | **No** (see below) | N/A by design |
| 3. Merchant content | `templates/*.json`, `sections/*group.json` | Via Shopify admin | **Generated, needs import** |

---

## Layer 1 — theme strings (done)

All shopper-visible hardcoded English in Liquid has been moved into the `fgp.*`
namespace and is rendered with the `t` filter. 99 keys, present and translated in
both `en.default.json` and `es.json`.

Covered: section `aria-label`s, mobile menu (nav, search, account, cart), hero
copy and CTAs, symptom lists, synbiotic/kids feature and spotlight copy,
newsletter and footer labels, "Read more", star labels, image `alt` text.

To add a new string:

```liquid
{{ 'fgp.my_section.my_key' | t }}
```

…then add `my_key` under `fgp.my_section` in **both** locale files. Keys must exist
in both or Shopify renders `translation missing`.

Where a translated string is used as a `| default:` fallback, it is assigned at the
top of the section (Liquid cannot call `t` inside `default:`):

```liquid
{%- assign fgp_syn_cta = 'fgp.synbiotic.cta_label' | t -%}
...
{{ section.settings.cta_label | default: fgp_syn_cta }}
```

Note that `{% render %}` creates an isolated scope, so these assigns must live in the
section file itself, not in `fgp-global`.

---

## Layer 2 — schema defaults (intentionally not translated)

Shopify writes a schema `default` into `templates/*.json` **once**, when a section is
first added. It is static content, not a runtime lookup, so it cannot vary by locale.
Converting these to `t:` keys would only translate the **theme editor UI** for the
merchant — it would not change a single word for a shopper.

They were therefore left as-is. Real page copy is Layer 3.

---

## Layer 3 — merchant content (generated — needs one import)

504 storefront strings live in `templates/*.json`. This is the actual page copy.
Shopify serves the Spanish version of these through **Translate & Adapt**, which
stores translations server-side rather than in theme files.

Spanish has been written for **all 504** — nothing needs to be translated by hand:

- **`translations-es.csv`** — every string with `file`, `section_type`, `json_path`,
  `setting`, `english`, `spanish`, `status`. Use this to review or paste into
  Translate & Adapt.
- **`translations/es/*.json`** — full Spanish copies of each template, ready to use.

Breakdown: 438 translated, 66 intentionally identical (brand names, `@handles`,
emails, reviewer names, Costa Rican place names). Nothing left to review.

### To apply

Recommended — **Translate & Adapt** (Shopify admin → Apps → Translate & Adapt →
Spanish → Theme). Auto-translate first, then correct against `translations-es.csv`.
This keeps one set of template files and is the supported path.

Alternative — if Spanish is served by a **separate theme**, copy
`translations/es/templates__*.json` over that theme's `templates/` (strip the
`templates__` / `sections__` prefix to recover the original path).

---

## Resolved: About page English copy

`templates/page.about.json` and `templates/page.json` previously held Spanish-only copy,
so English visitors saw Spanish. English has now been **authored and applied** — the
Spanish was the original source copy, so this was a translation job rather than writing
from nothing:

- `templates/page.about.json` — 11 strings (eyebrows, headings, hero subtext, mission
  body, founder bio, CTAs, image alt)
- `templates/page.json` — the 6-paragraph About narrative in the `image-with-text` block

The Spanish originals are preserved verbatim in `translations/es/` so no source copy was
lost. `templates/page.contact.json` was already fully English and needed no work.

**This is authored marketing copy — please read it once before launch** and adjust tone or
claims to taste. It is a faithful translation, not a rewrite.

## Needs a human decision

1. **Placeholder content still in templates**, which should be real copy before launch
   rather than translated as-is:
   - `Dr. Name Lastname` (10 occurrences), `Product name`, `Button label`, `Feature`
   - `+506 XXXX XXXX` in `page.contact.json`

2. **`fgp-comparison-table`** — `Upto-proliferating` and `Only strains to sleep` appear
   to be garbled in the English source. Translated literally; both should be reworded.

3. **Fixed along the way (not translation-related):** `sections/hero-split.liquid` had a
   trailing comma in its `{% schema %}` making the JSON invalid — that section would have
   failed to load in Shopify. Also `sections/main-login.liquid` had hardcoded Spanish
   (`¿No tienes cuenta?`) shown to English users, and `general.meta.tags` / `general.meta.page`
   were referenced by `layout/theme.liquid` but missing from every locale, so tag and
   paginated pages rendered `translation missing` in the `<title>`.
