# Translations — EN / ES

The site targets **Spanish** and **English** only.

**Spanish is the store's default language** (Settings → Languages). English is the
*localized* layer, served through Translate & Adapt. Default content therefore lives
in Spanish in `templates/*.json`; English is an overlay on top of it.

Text on this theme lives in three separate layers, and only two of them are controlled
by files in this repo.

| Layer | Where it lives | Locale-aware? | Status |
|---|---|---|---|
| 1. Theme strings | `locales/en.default.json`, `locales/es.json` | Yes — via `\| t` | **Done** |
| 2. Schema `default` values | `{% schema %}` in each section | **No** (see below) | N/A by design |
| 3. Merchant content | `templates/*.json` (Spanish base) | English via Shopify admin | **Spanish applied; English needs import** |

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

## Layer 3 — merchant content

504 storefront strings live in `templates/*.json`. This is the actual page copy.

**`templates/*.json` now holds Spanish** — 414 values were converted so the default
content matches the store's default language. Verified: 223 Spanish strings, 0 English
remaining, all JSON valid.

**English is the overlay**, delivered via Translate & Adapt:

- **`translations-en.csv`** — 504 rows: `file`, `section_type`, `json_path`, `setting`,
  `spanish_default`, `english_translation`, `status`.
  414 translated, 90 identical (brand names, `@handles`, emails, reviewer names,
  Costa Rican place names).

### To apply the English layer

1. In Translate & Adapt, **delete the auto-generated English layer**. It was produced
   while `templates/*.json` was still English, so it translated English → English and is
   a copy, not a translation. It is also now stale against the Spanish base.
2. Import `translations-en.csv`, or paste its `english_translation` column.

Do not re-run auto-translate for English: the reviewed copy in `translations-en.csv`
includes hand-written About-page copy that machine translation will overwrite.

### Direction note

An earlier pass had this backwards — templates in English with a Spanish overlay. That
was corrected once the store's default language was confirmed as Spanish. The obsolete
`translations/es/` and `translations-es.csv` were removed.

---

## About page copy

The About narrative exists in both languages. Spanish is the authored original and is
what now sits in `templates/page.about.json` and `templates/page.json` (the 6-paragraph
block in `image-with-text`).

English was written by hand for these — 11 strings on the About page plus the 6
paragraphs — and lives in `translations-en.csv`. It is a faithful translation of the
Spanish, not machine output.

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
