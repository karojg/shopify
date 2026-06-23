# Figma Design System — Stressbiotic Landing Page
## Feel Good Pharma · Full Frame Documentation
Figma file: `Hbqe4bPiZLB95ssvhQ4ZeW` · Section node: `367:1370` · Extracted 2026-06-22

See `design-tokens.md` for global color palette, typography scale, spacing, and border-radius tokens.

---

## Table of Contents
1. [Global Layout & Pages](#global)
2. [Desktop — Hero Frames](#desktop-heroes)
3. [Desktop — Full Page (FGP_Formulations_Synbiotic_1920_V3)](#desktop-full)
4. [Mobile — Hero Frames](#mobile-heroes)
5. [Mobile — Full Page (Stressbiotic_PLP_V3)](#mobile-full)
6. [Mobile — SlideMenu Component](#slide-menu)
7. [Shopify Section Mapping](#shopify-mapping)

---

<a id="global"></a>
## 1. Global Layout & Pages

| Frame Name | Node ID | Canvas Size | Variant |
|---|---|---|---|
| FGP_Formulations_Synbiotic_1920_V3 | 303:10880 | 1920 × 8383px | Desktop |
| Stressbiotic_PLP_V3 | 303:12066 | 375 × 7535px | Mobile |
| Hero 02_V2 | 303:13695 | 1920 × 900px | Desktop Hero |
| Hero 03_V2 | 303:13714 | 1920 × 900px | Desktop Hero Alt |
| Hero 01_Mobile | 303:13775 | 375 × 856px | Mobile Hero |
| Hero 03_Mobile | 303:13797 | 375 × 495px | Mobile Hero Alt |
| SlideMenu | 303:13351 | 280 × 634px | Mobile Nav Overlay |

---

<a id="desktop-heroes"></a>
## 2. Desktop — Hero Frames

---

### Frame: Hero 02_V2
**Node ID:** `303:13695` · **Size:** 1920 × 900px · **Variant:** Desktop

**Layout:**
- Full-width hero. Content column left-aligned; product bottle image right side.
- Two-column split: left ~50% (text + CTAs), right ~50% (product photo + trust badge).
- bg: `#234092` (Dark Cornflower Blue), overflow hidden.
- Decorative "Gut Line Blue" illustration positioned top-right.

**Colors:**
- Background: `#234092`
- Headline text: `#ffffff`
- Eyebrow label: `rgba(255,255,255,0.8)` or `#f8f8f8`
- CTA "Learn More" button bg: `#45bfef`, text: `#234092`
- CTA "Shop Now" button bg: `#fed304`, text: `#234092`
- Benefit pills border + text: `#99dbfc`
- Trust badge "Recommended By" is white/transparent overlay

**Typography:**
- Eyebrow label: Poppins Light 24px — "Plant-based Psychobiotic"
- H1 Line 1: Poppins Bold 96px — "Your mind & gut,"
- H1 Line 2: Poppins Bold 96px — "finally made peace."
- Subtitle: Poppins Regular 40px — "Digestive Stress Psychobiotic"
- Benefit pills: Poppins Medium 24px (pill-shaped badges, `border-radius: 200px`)
- CTA buttons: Poppins SemiBold 24px, `letter-spacing: 1px`

**Spacing / Sizing:**
- Content left-pad: ~108px
- H1 margin-top: ~60px
- CTA row gap: 30px
- Benefit pills gap: 16px
- CTA area margin-top: ~40px

**Copy / Text Content:**
- Eyebrow: "Plant-based Psychobiotic"
- H1: "Your mind & gut, finally made peace."
- Subtitle: "Digestive Stress Psychobiotic"
- Benefit pills: "Psychobiotic" · "Postbiotics" · "Prebiotics" · "Probiotics" · "Digestive Enzymes"
- CTA 1: "Learn More"
- CTA 2: "Shop Now"

**Component Structure:**
- `HeroFrame` → `ContentColumn` (eyebrow + H1 + subtitle + benefits + CTAs) + `ProductColumn` (bottle image + trust badge)

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` — schema blocks: `heading`, `subheading`, `cta_primary`, `cta_secondary`, `benefit_pills[]`, `product_image`, `badge_image`

---

### Frame: Hero 03_V2
**Node ID:** `303:13714` · **Size:** 1920 × 900px · **Variant:** Desktop Alternate

**Layout:**
- Full-width hero. Three Stressbiotic bottles centered. Text + CTA in left column.
- Left content column: heading + symptom list + CTA. Center-right: three product bottles stacked/layered.
- bg: `#45bfef` (Picton Blue).

**Colors:**
- Background: `#45bfef`
- H1 text: `#234092`
- Symptom text: `#2e2a39`
- CTA button bg: `#234092`, text: `#ffffff`
- Benefit tag bg: `#f8f8f8`, text: `#234092`

**Typography:**
- H1: Poppins SemiBold 79.174px — "Is it a gut feeling or ___?"
- H1 blank fill (symptom cycling): same size/weight, implied animated fill
- Symptom list items: Poppins SemiBold 46.185px (large checklist)
- CTA button: Poppins SemiBold 31.67px

**Spacing / Sizing:**
- Left content column: `~108px` left pad
- Symptom list item gap: ~16px
- Bottles: centered, overlapping, layered with drop shadows

**Copy / Text Content:**
- H1: "Is it a gut feeling or ___?"
- Symptom list (with checkmarks):
  - ✓ "Stress"
  - ✓ "Anxiety"
  - ✓ "Poor Sleep"
  - ✓ "Bloating"
  - ✓ "Constipation"
  - ✓ "Low Energy"
- CTA: "Take The 1 Minute Test!"

**Component Structure:**
- `HeroAlt` → `ContentCol` (heading + checked symptom list + CTA) + `ProductBottlesCol` (3× layered bottle images)

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` with `variant: "symptom-quiz"` block — or use as alternate hero section

---

<a id="desktop-full"></a>
## 3. Desktop — Full Page (FGP_Formulations_Synbiotic_1920_V3)
**Node ID:** `303:10880` · **Canvas:** 1920 × 8383px

Sub-sections below are in vertical order (top → bottom of the page).

---

### Section: Desktop Header
**Node ID:** `303:10881` · **Height:** ~80px

**Layout:** Full-width fixed/sticky nav bar. Logo left, nav links center, icons right.

**Colors:** Background `#45bfef`; nav link text `#234092`; active link `#234092` SemiBold; icon color `#234092`

**Typography:** Poppins Regular 16px `letter-spacing: 0.6px` for nav links; active state SemiBold

**Copy:**
- Nav links: "Home" · "Formulations" · "Science Behind It" · "About Us"
- Icon group (right): search icon + cart icon

**Shopify Mapping:** `sections/header.liquid` — standard Shopify Dawn header override. bg color override via CSS.

---

### Section: Desktop ProductInfo (Product Detail / PDP Hero)
**Node ID:** `303:11570` · **Height:** ~900px

**Layout:**
- Two-column: left = product gallery thumbnails (vertical strip) + main product image; right = product detail form.
- Background: `#234092`
- Right column sits at ~px 960 with right pad `108px`.

**Colors:**
- Background: `#234092`
- Product title + price: `#ffffff`
- Brand label: `rgba(255,255,255,0.7)`
- "Shipping + Taxes" note: `rgba(255,255,255,0.7)` Poppins Light
- Quantity stepper bg: `#fdb921`, text: `#234092`
- "Add to Cart" button bg: `#144ca1`, text: `#ffffff`
- "Buy it now" button bg: `#fdb921`, text: `#234092`
- Subscribe & Save radio border: `#ffffff`, bg active: `#ffffff`
- Price (subscribe): green `#4caf50` or white variation
- "SAVE 5%" badge bg: `#fed83f`

**Typography:**
- Brand: Poppins Light 16.8px — "Stressbiotic® Digestive Stress Psychobiotic"
- Product H1: Poppins SemiBold 44px `letter-spacing: 0.66px` — "Stressbiotic Digestive Enzymes"
- Price: Poppins Regular 20px `letter-spacing: 1.365px`
- Shipping: Poppins Light 12.6px `letter-spacing: 0.735px`
- Quantity label: Poppins Light 13.7px `letter-spacing: 0.42px`
- Purchase options: Nunito Bold/Light 16.8px
- Add to Cart: Poppins Light 15.8px `letter-spacing: 1.05px`
- Buy It Now: Poppins Medium 15.8px `letter-spacing: 1.05px`
- Subscription save: Nunito Bold 16.8px

**Spacing:**
- Right column padding: `108px` right, `60px` top
- Quantity stepper: pill shape, `border-radius: 100px`
- Button gap: `8px`
- Buttons: `border-radius: 41px`, full-width

**Copy / Text Content:**
- Brand: "Stressbiotic® Digestive Stress Psychobiotic"
- H1: "Stressbiotic Digestive Enzymes"
- Size: "60 Capsules"
- Price one-time: "$75.00"
- Price subscribe: "$71.25"
- Note: "Free Shipping + Taxes included"
- Purchase options:
  - "One Time Purchase — $75.00"
  - "Subscribe & Save 5% — $71.25 / month"
- Quantity: "QUANTITY" (stepper 1–99)
- CTA 1: "Add to Cart"
- CTA 2: "Buy it now"
- Accordion items (below form):
  - "Dosage" (content: recommended dosage info)
  - "Shipping" (content: shipping policy)
  - "Return Policy" (content: return terms)

**Shopify Mapping:** `sections/featured-product.liquid` or `sections/main-product.liquid` — standard Shopify product form with subscription app (e.g. Recharge/Smartrr) purchase option block.

---

### Section: Desktop Info Bar (Product Benefit Badges)
**Node ID:** `303:11648` · **Height:** ~120px

**Layout:** Full-width horizontal strip. 6 icon+label columns, evenly distributed.

**Colors:** Background `#f8f8f8`; icon color `#234092`; text `#234092`

**Typography:** Poppins SemiBold 14–16px centered labels

**Copy (6 badges, left → right):**
1. Spore based probiotics
2. Plant Based
3. Replenishes Beneficial Bacteria
4. Strengthens Gut Barrier
5. Improves Nutrient Absorption
6. Non GMO

**Component Structure:** `BenefitBar` → 6× `{icon + label}` flex-row items

**Shopify Mapping:** `sections/fgp-product-benefits.liquid` — icon+label repeater block

---

### Section: Desktop Ingredients
**Node ID:** `303:11649` · **Height:** ~800px

**Layout:**
- Full-width, centered content.
- Heading + subtitle centered top.
- 4-column grid of ingredient cards below.
- bg: `#ffffff`

**Colors:**
- Background: `#ffffff`
- Section H2: `#65438a` (Cyber Grape)
- Card heading: `#234092`
- Card body: `#2e2a39`
- Card icon bg: transparent (SVG icons)

**Typography:**
- Section label (eyebrow): Poppins Medium 20px `letter-spacing: 0.78px` — "Our Stressbiotic Formula"
- H2: Poppins SemiBold 40px `letter-spacing: -0.68px` — "Formulated with the Best Ingredients"
- Card ingredient name: Inter SemiBold 24px `letter-spacing: 0.86px`
- Card body: Poppins Regular 18px `letter-spacing: 0.66px`

**Spacing:**
- Section `py: 100px`, `px: 108px`
- Card grid gap: `40px`
- Icon-to-text gap: `26.5px`

**Copy:**
- Eyebrow: "Our Stressbiotic Formula"
- H2: "Formulated with the Best Ingredients"
- Card 1: "Psychobiotic Postbiotics" — description (neurotransmitter/mood support)
- Card 2: "Bateriophage Prebiotic" — description (prebiotic fiber support)
- Card 3: "Aswhaganda" (sic) — description (adaptogen stress reduction)
- Card 4: "Enzyme Blend" — description (digestive enzyme support)

**Shopify Mapping:** `sections/fgp-product-benefits.liquid` with 4-column layout variant, or dedicated `sections/fgp-ingredients.liquid`

---

### Section: Desktop How Formulations Work
**Node ID:** `303:11709` · **Height:** ~650px

**Layout:**
- Full-width. Centered heading + 4-step horizontal process flow.
- bg: `#f8f8f8`
- 4 columns with step number + heading + body copy

**Colors:**
- Background: `#f8f8f8`
- H2: `#65438a`
- Step heading: `#234092`
- Step body: `#2e2a39`
- Step number: `#45bfef` or circle badge

**Typography:**
- H2: Poppins SemiBold 40px — "How our formulations work?"
- Step heading: Poppins SemiBold 24px `letter-spacing: 0.78px`
- Step body: Poppins Regular 18px `letter-spacing: 0.78px`

**Copy:**
- H2: "How our formulations work?"
- 4 steps with placeholder/product copy (step descriptions relate to psychobiotic mechanism of action)

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` 4-step process variant, or custom `sections/fgp-how-it-works.liquid`

---

### Section: Desktop Banner / Benefit Strip
**Node ID:** `303:11738` · **Height:** ~600px

**Layout:**
- Two-column: Left = heading + benefit list; Right = product bottle image on colored bg.
- bg: `#234092` left panel; right panel: `#18b5f3` (bright blue) with floating product image
- Benefit list: vertical, with checkmark icons

**Colors:**
- Left bg: `#234092`
- Right bg: `#18b5f3`
- Heading text: `#ffffff`
- Benefit text: `#ffffff`
- Checkmark icons: `#fed304` or `#fdb921`

**Typography:**
- H2: Poppins SemiBold 40px — "Your journey to wellness..."
- Benefit items: Poppins Regular 18–20px

**Copy:**
- H2: "Your journey to wellness starts here."
- Benefits (checkmark list):
  - "Improves sleep"
  - "Reduce Stress"
  - "Supports Gut Health"
  - "Adaptogen and Psychobiotic"
  - "Supports IBS Patients"

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` two-panel variant — or `sections/main-collection-product-grid.liquid` override

---

### Section: Desktop Comparison Table
**Node ID:** `303:11803` · **Height:** ~1100px

**Layout:**
- Centered content, max-width container.
- H2 top-centered. Below: comparison table card (white bg, `border-radius: 24px`).
- 3 columns: Feature name | Stressbiotic® (highlighted `#f6f9ea`) | Other Products (`#ebebeb`)
- 10 rows of features.
- bg: `#ffffff`

**Colors:**
- Background: `#ffffff`
- H2: `#65438a`
- Table header: `#234092` text on `#f6f9ea` (Stressbiotic) / `#ebebeb` (Other)
- Row bg: alternating `#f6f9ea` / `#ebebeb`
- Check/X marks: `#4caf50` (green check) / `#e53935` (red X) or icon SVGs
- Table card `border-radius: 24px`

**Typography:**
- H2: Poppins SemiBold 40px `letter-spacing: -0.68px` — "How Stressbiotic® compares"
- Table heading: Poppins SemiBold 16px
- Table cell: Poppins SemiBold 16px / Regular 12px sub-notes

**Copy:**
- H2: "How Stressbiotic® compares"
- Subheading: "Trusted by thousands. Backed by science."
- Column headers: "Feature" · "Stressbiotic®" · "Other Products"
- 10 comparison rows (attributes like: "Psychobiotics", "Postbiotics", "Prebiotics", "Digestive Enzymes", "Plant-Based", "Non-GMO", "Spore-Based Probiotics", "Bacteriophage Prebiotics", "Ashwagandha", "Clinical doses")

**Shopify Mapping:** Custom `sections/main-collection-product-grid.liquid` table variant — or static Liquid section with comparison table block

---

### Section: Desktop Who Is It For
**Node ID:** `303:11843` · **Height:** ~900px

**Layout:**
- Full-width. H2 centered top. Below: 4-column grid of "Who Is It For" cards.
- bg: `#f8f8f8`
- Each card: white bg, pill-shaped labels, `border-radius: 27.264px`

**Colors:**
- Background: `#f8f8f8`
- H2: `#65438a`
- Card bg: `#ffffff`
- "FOR" pill: `#45bfef` bg, `#ffffff` text
- Card heading: `#234092`
- Card body: `#2e2a39`
- Benefit claim pills: `#f8f8f8` bg, `#234092` text (small labels at bottom of card)

**Typography:**
- Section H2: Poppins SemiBold 40px — "Is Stressbiotic® for You?"
- Card "FOR" label: Poppins Medium 12px uppercase `letter-spacing: 0.68px`
- Card title: Poppins SemiBold 24px `letter-spacing: 1.33px`
- Card body: Poppins Regular 16px `letter-spacing: 0.68px`
- Claim pills: Poppins Medium 8.52px `letter-spacing: 0.68px`

**Spacing:**
- Card padding: `27.264px` all sides
- Card grid gap: `40px` (responsive)
- Section `py: 100px`, `px: 108px`

**Copy:**
- H2: "Is Stressbiotic® for You?"
- Card 1: FOR "Busy Professionals" — "Business people" — body: stress + focus description
- Card 2: FOR "Gut Health" — "IBS patients" — body: digestive health description
- Card 3: FOR "Mental Wellness" — "Very stressed people" — body: anxiety + sleep description
- Card 4: FOR "Better Sleep" — "Sleep-troubled patients" — body: sleep quality description

**Shopify Mapping:** `sections/fgp-products-grid.liquid` with card variant — or custom `sections/fgp-benefits-for.liquid`

---

### Section: Desktop Products Add (Related Products)
**Node ID:** `303:11932` · **Height:** ~850px

**Layout:**
- Centered. H2 centered top. 3-column product card grid.
- bg: `#ffffff`
- Product cards: white bg, rounded corners `border-radius: 24px`, image top, text below

**Colors:**
- Background: `#ffffff`
- H2: `#65438a`
- Card bg: `#ffffff`
- Card category text: `#8e8e93` (muted gray)
- Card product name: `#234092`
- Card price: `#303c43`
- "Add" button bg: `#234092`, text `#ffffff`

**Typography:**
- H2: Poppins SemiBold 40px — "Your Gut's New Best Friends"
- Card category: Poppins Regular 11px uppercase `letter-spacing: 1.1px`
- Card name: Poppins SemiBold 24px `line-height: 30px`
- Card price: Poppins Regular 16px `line-height: 15px`
- Add button: Poppins SemiBold 16px `letter-spacing: 1px`

**Spacing:**
- Section `py: 100px`, `px: 200px`
- Card grid gap: `30–40px`
- Card `border-radius: 16–24px`

**Copy:**
- H2: "Your Gut's New Best Friends"
- Card 1: "DIGESTIVE ENZYMES" · "Digestive Enzymes Synbiotic+" · "$65" · [Add button]
- Card 2: "PROBIOTICS" · "Kids Probiotic Gummies" · "$75" · [Add button]
- Card 3: "ACCESSORIES" · "Magnetic Pill Boxes" · "$16" · [Add button]

**Shopify Mapping:** `sections/featured-collection.liquid` — standard Shopify collection grid (3 products)

---

### Section: Desktop Video
**Node ID:** `303:11996` · **Height:** ~600px

**Layout:**
- Centered max-width container. Video card with play button overlay.
- bg: `#f8f8f8`; card bg: `#fdfbf7`; `border-radius: 24px`; `box-shadow: 10px 10px 17.5px rgba(46,42,57,0.05)`

**Colors:**
- Section bg: `#f8f8f8`
- Card bg: `#fdfbf7`
- Play button: `#fdfbf7` bg with border `rgba(46,42,57,0.1)`
- Play icon: `#234092`

**Typography:** No text copy in this section (video only)

**Copy:** No text content visible (video thumbnail + play button)

**Shopify Mapping:** `sections/video.liquid` — standard Shopify video section with embed URL

---

### Section: Desktop FAQs
**Node ID:** `303:12002` · **Height:** ~700px

**Layout:**
- Centered max-width. H2 top-centered. 4 accordion items stacked vertically.
- bg: `#ffffff`; accordion item bg: `#f8f8f8`; `border-radius: 20px`

**Colors:**
- Background: `#ffffff`
- H2: `#65438a`
- Accordion item bg: `#f8f8f8`
- Question text: `#234092`
- Answer text: `#2e2a39`
- Chevron icon: `#234092`

**Typography:**
- H2: Poppins SemiBold 40px `letter-spacing: -0.68px, line-height: 42px`
- Question: Poppins SemiBold 20px `letter-spacing: 0.66px, line-height: 21.23px`
- Answer label: Poppins Bold 14px `letter-spacing: 0.63px`
- Answer body: Poppins Regular 14px `letter-spacing: 0.63px, line-height: 1.45`

**Spacing:**
- Section `py: 80px`, `px: 108px`
- Accordion item padding: `24px` sides, `20px` top/bottom
- Accordion gap: `12px`

**Copy:**
- H2: "You've got questions? We've got answers"
- FAQ 1 Q: "What makes Stressbiotic different from other supplements?"
- FAQ 1 A: [answer about psychobiotic formula]
- FAQ 2 Q: "How long before I see results?"
- FAQ 2 A: [answer about 4–6 weeks]
- FAQ 3 Q: "Is it safe to take every day?"
- FAQ 3 A: [answer about daily use]
- FAQ 4 Q: "Can I take it with other medications?"
- FAQ 4 A: [answer recommending consulting physician]

**Shopify Mapping:** `sections/collapsible-content.liquid` — standard Shopify collapsible content section (accordion blocks)

---

### Section: Desktop Medical Reviews (Doctors)
**Node ID:** `303:12042` · **Height:** ~700px

**Layout:**
- Full-width. H2 centered top. 3-column doctor review card grid.
- bg: `#f8f8f8`
- Doctor cards: white bg, `border-radius: 16px`, `box-shadow: 0px 4px 3px rgba(0,0,0,0.08)`

**Colors:**
- Section bg: `#f8f8f8`
- H2: `#65438a`
- Card bg: `#ffffff`
- Doctor name: `#252f35`
- Doctor role/specialty: `#8e8e93`
- Review text: `#303c43`
- Star rating: `#ffaa47`
- Quote icon: `#45bfef` or `#234092`

**Typography:**
- H2: Poppins SemiBold 40px — "Recommended by Doctors"
- Doctor name: Poppins SemiBold 18px `line-height: 26px, letter-spacing: -0.36px`
- Specialty: Poppins Regular 14px `line-height: 26px, letter-spacing: -0.36px`
- Handle/social: Poppins Regular 12px `line-height: 26px, letter-spacing: -0.36px`
- Quote: Poppins Regular 16px `line-height: 20px`
- Stars: Times Regular 18px (★ characters)

**Copy:**
- H2: "Recommended by Doctors"
- Doctor 1: "Dra. Nancy Conejo" · Specialty · handle · 5-star review quote
- Doctor 2: "Dra. Von Saalfeld" · Specialty · handle · 5-star review quote
- Doctor 3: "Dra. Andrea Masís" · Specialty · handle · 5-star review quote

**Shopify Mapping:** Custom `sections/main-product.liquid` testimonial variant, or `sections/multicolumn.liquid` with review card block type

---

### Section: Desktop Customer Reviews
**Node ID:** `303:12043` · **Height:** ~600px

**Layout:**
- Full-width. H2 + aggregate star rating centered top. 4 review cards (2×2 grid or horizontal scroll).
- bg: `#f8f8f8`
- Review cards: white bg, `border-radius: 16px`, `box-shadow: 0px 4px 3px rgba(0,0,0,0.08)`

**Colors:**
- Section bg: `#f8f8f8`
- H2: `#65438a`
- Aggregate rating stars: `#ffaa47`
- Card bg: `#ffffff`
- Reviewer name: `#252f35`
- Review body: `#303c43`
- Stars: `#ffaa47`

**Typography:**
- H2: Poppins SemiBold 40px — "Loved by Customers"
- Aggregate rating: Poppins SemiBold 20px
- Reviewer name: Poppins SemiBold 18px
- Review body: Poppins Regular 16px

**Copy:**
- H2: "Loved by Customers"
- Aggregate: "4.9 ★★★★★ (500+ reviews)" (approximate)
- 4 review cards with star rating, reviewer name, review body text

**Shopify Mapping:** `sections/multicolumn.liquid` or Shopify Reviews app integration block

---

### Section: Desktop Background Strip (Brand Marquee)
**Node ID:** `303:12044` · **Height:** ~80px

**Layout:**
- Full-width horizontal strip. Repeating text marquee or static centered text.
- bg: `#fdb921` (Orange Yellow)
- Contains brand tagline + hashtag + Instagram handle

**Colors:**
- Background: `#fdb921`
- Text: `#234092`

**Typography:**
- Tagline: Poppins Regular 14px `letter-spacing: 0.6px`
- Hashtag: Poppins Bold ~15.875px `letter-spacing: 0.6px`
- Handle: Poppins SemiBold 15.25px `line-height: 32px, letter-spacing: 0.6px`

**Copy:**
- "Feel Good Pharma takes care of your microbiota..."
- "#FeelGoodWithin"
- Instagram: "feel.goodpharma"

**Shopify Mapping:** `sections/announcement-bar.liquid` or `sections/fgp-hero-banner.liquid` strip variant

---

### Section: Desktop Footer
**Node ID:** `303:12059` · **Height:** ~420px

**Layout:**
- Full-width footer. 3–4 columns: Logo + tagline | Company links | Resources links | Email subscribe form.
- Bottom bar: copyright + payment icons
- bg: `#234092`

**Colors:**
- Background: `#234092`
- Logo: white variant
- All text: `#ffffff`
- Column headings: `#ffffff` Medium
- Links: `#ffffff` Regular, hover: `#45bfef`
- Email subscribe input: white bg, `#234092` text, submit button `#fdb921`
- Payment icons: white/muted
- Divider: `rgba(255,255,255,0.2)`

**Typography:**
- Column heading: Poppins Medium 17px `line-height: 17px`
- Links: Poppins Regular 15px `line-height: 24px`
- Subscribe H2: Poppins Medium 24px `line-height: 17px`
- Subscribe sub: Poppins Regular 12px `line-height: 24px`
- Copyright: Poppins Regular 12px `line-height: 22.4px`

**Spacing:** `py: 60px`, `px: 108px`; link column gap: `14px`

**Copy:**
- Logo: FeelGoodPharma_Logo_Celeste (white SVG)
- Tagline: "Feel Good Within"
- Column "Company": Home · Formulations · Science Behind It · About Us
- Column "Resources": FAQ · Reviews · Contact Us · Privacy Policy · Terms of Service
- Subscribe: "Join the Feel Good Community"
- Subscribe sub: "Get updates, wellness tips, and exclusive offers."
- Input placeholder: "Your email address"
- Button: "Subscribe"
- Copyright: "© 2025 Feel Good Pharma. All Rights Reserved."
- Payment icons: Visa · Mastercard · Amex · PayPal · Apple Pay · Google Pay

**Shopify Mapping:** `sections/footer.liquid` — Shopify Dawn footer. Add email subscribe to newsletter block.

---

### Section: Desktop Sticky Add to Cart
**Node ID:** `303:12060` · **Height:** ~80px

**Layout:**
- Fixed bottom bar. Product name + price left; ATC + BIN buttons right.
- bg: `#f8f8f8` (light bar)

**Colors:**
- Bar bg: `#f8f8f8`
- Product name text: `#234092`
- "Add to Cart" btn bg: `#144ca1`, text `#ffffff`
- "Buy It Now" btn bg: `#fdb921`, text `#234092`

**Typography:**
- Product name: Poppins SemiBold 18px
- Price: Poppins Regular 16px
- Buttons: Poppins SemiBold 20px `letter-spacing: 1px`

**Copy:**
- Product: "Stressbiotic Digestive Enzymes"
- Price: "$75.00"
- CTA 1: "Add to Cart"
- CTA 2: "Buy It Now"

**Shopify Mapping:** Custom sticky JS component in `assets/sticky-atc.js` + Liquid snippet `snippets/sticky-atc.liquid`

---

<a id="mobile-heroes"></a>
## 4. Mobile — Hero Frames

---

### Frame: Hero 01_Mobile
**Node ID:** `303:13775` · **Size:** 375 × 856px · **Variant:** Mobile

**Layout:**
- Full mobile hero. Left-aligned content. Product bottle bottom-right.
- bg: `#234092`; bottom corners: `border-bottom-left-radius: 30px; border-bottom-right-radius: 30px`

**Colors:**
- Background: `#234092`
- H1 text: `#ffffff`
- Eyebrow: `rgba(255,255,255,0.8)`
- CTA "Learn More" bg: `#45bfef`, text: `#234092`
- CTA "Shop Now" bg: `#fed304`, text: `#234092`
- Benefit pills border: `#99dbfc`, text: `#99dbfc`

**Typography:**
- Eyebrow: Poppins Light 14px
- H1: Poppins Bold 32px `line-height: 1.2`
- Benefits pills: Poppins Medium 14px
- CTA buttons: Poppins SemiBold 14px `letter-spacing: 1px`

**Spacing:** Content `px: 20px`; hero height 856px; CTA row gap: `12px`; benefit pill gap: `8px`

**Copy:**
- Eyebrow: "Plant-based Psychobiotic"
- H1: "Your mind & gut, finally made peace."
- Benefit pills: "Psychobiotic" · "Postbiotics" · "Prebiotics" · "Probiotics" · "Digestive Enzymes"
- CTA 1: "Learn More"
- CTA 2: "Shop Now"

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` with mobile breakpoint styles

---

### Frame: Hero 03_Mobile
**Node ID:** `303:13797` · **Size:** 375 × 495px · **Variant:** Mobile Alternate

**Layout:**
- Condensed mobile hero. 3 product bottles centered top. Text block below bottles.
- bg: `#45bfef`; bottom corners: `border-bottom-left-radius: 30px; border-bottom-right-radius: 30px`
- Bottles overlapping, slight drop shadow.

**Colors:**
- Background: `#45bfef`
- Heading text: `#234092`
- Symptom text: `#2e2a39`
- CTA bg: `#234092`, text: `#ffffff`

**Typography:**
- Heading: Poppins SemiBold 20px `line-height: 32px`
- Symptom list: Poppins Regular 16px
- CTA: Poppins SemiBold 12px `letter-spacing: 1px`

**Copy:**
- Heading: "Is it a gut feeling or ___?"
- Symptom list: Stress · Anxiety · Poor Sleep · Bloating · Constipation · Low Energy
- CTA: "Take The 1 Minute Test!"

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` — alternate mobile hero variant

---

<a id="mobile-full"></a>
## 5. Mobile — Full Page (Stressbiotic_PLP_V3)
**Node ID:** `303:12066` · **Canvas:** 375 × 7535px

---

### Section: Mobile Header
**Node ID:** `303:12067` · **Height:** ~60px

**Layout:** Full-width fixed nav. Hamburger menu icon left, FGP logo center, search+cart icons right.

**Colors:** Background `#45bfef`; icons `#234092`; logo text `#234092`

**Typography:** Nav icons only (no text links visible in closed state)

**Component Structure:** `MobileHeader` → `HamburgerIcon` + `Logo` + `IconGroup` (search + cart)

**Shopify Mapping:** `sections/header.liquid` mobile breakpoint, hamburger trigger opens SlideMenu

---

### Section: Mobile Product Gallery
**Node ID:** `303:12105` · **Height:** ~480px

**Layout:**
- Full-width product image area. Single main image with thumbnail strip below.
- bg: `#234092` or gradient from hero above.
- Thumbnails: horizontal row at bottom of gallery

**Colors:** Main image area bg: dark blue continuation; thumbnails: white border highlight on active

**Copy:** No text content (image gallery only)

**Shopify Mapping:** Standard Shopify product media gallery component

---

### Section: Mobile ProductInfo
**Node ID:** `303:12787` · **Height:** ~700px

**Layout:**
- Full-width, single-column product form.
- bg: `#234092`
- Brand label → H1 → reviews badge → price → purchase options → quantity → CTAs → description

**Colors:**
- Background: `#234092`
- All text: `#ffffff`
- Quantity stepper bg: `#fdb921`
- Add to Cart bg: `#f8f8f8`, text: `#234092`
- Buy It Now bg: `#fdb921`, text: `#234092`
- SAVE badge: `#fed83f`

**Typography:**
- Brand: Poppins Regular 12px `letter-spacing: 0.78px`
- H1: Poppins SemiBold 28px `letter-spacing: 0.5px`
- Rating: Poppins Regular 12–14px
- Price: Inter SemiBold 18px `line-height: 27px`
- Options label: Inter Medium 13px
- Quantity: Inter Medium 13px
- CTA: Poppins SemiBold 15px `letter-spacing: 1.05px`
- Description: Poppins Regular 14px `letter-spacing: 0.5px, line-height: 1.5`

**Copy:**
- Brand: "Stressbiotic® Digestive Stress Psychobiotic"
- H1: "Stressbiotic Digestive Enzymes"
- Rating: "★★★★★ 4.9 (500+ Reviews)"
- One-time: "$75.00"
- Subscribe: "$71.25 / month"
- Subscription note: "SAVE 5%"
- Quantity label: "QUANTITY"
- CTA 1: "Add to Cart"
- CTA 2: "Buy it now"
- Shipping: "Free Shipping · Taxes included"
- Description: product description paragraph

**Shopify Mapping:** `sections/featured-product.liquid` — mobile product form, same schema as desktop

---

### Section: Mobile Dosage/Accordions
**Node ID:** `303:12834` · **Height:** ~300px

**Layout:** 3 stacked accordion items (Dosage / Shipping / Return Policy). Same style as desktop accordions.

**Colors:** Accordion item bg: `#f8f8f8`; label text: `#234092`; chevron: `#234092`

**Typography:** Label: Poppins SemiBold 16px; Body: Poppins Regular 14px

**Copy:**
- "Dosage" — dosage instructions
- "Shipping" — shipping info
- "Return Policy" — return terms

**Shopify Mapping:** Accordion blocks within `sections/featured-product.liquid` (collapsible tab component)

---

### Section: Mobile Ingredients
**Node ID:** `303:12855` · **Height:** ~1200px

**Layout:**
- Single-column. Heading + subtitle centered. 4 ingredient cards stacked vertically.
- bg: `#ffffff`
- Each card: icon top, name heading, description body

**Colors:** Same as desktop: H2 `#65438a`, card heading `#234092`, body `#2e2a39`

**Typography:**
- H2: Poppins SemiBold 28–32px
- Card name: Poppins SemiBold 18–20px
- Card body: Poppins Regular 14px

**Copy:** Same 4 ingredients as desktop (Psychobiotic Postbiotics / Bateriophage Prebiotic / Aswhaganda / Enzyme Blend)

**Shopify Mapping:** `sections/fgp-product-benefits.liquid` — single-column mobile variant

---

### Section: Mobile QuoteBanner
**Node ID:** `303:12920` · **Visibility:** Hidden (not rendered in production)

**Note:** This frame is hidden in the Figma design — skip in implementation.

---

### Section: Mobile HealthCard
**Node ID:** `303:12926` · **Height:** ~450px

**Layout:**
- Full-width card. Header image or illustration. Below: heading + benefit list.
- bg: `#234092` or dark blue panel
- Card with rounded corners, benefit items as checkmark list

**Colors:** Card bg: `#234092`; text: `#ffffff`; checkmarks: `#fdb921`

**Typography:** H2: Poppins SemiBold 24–28px; benefit items: Poppins Regular 14–16px

**Copy:**
- H2: "Your journey to wellness starts here." (same as desktop banner)
- Benefit list: same 5 items (Improves Sleep / Reduce Stress / Supports Gut Health / Adaptogen and Psychobiotic / Supports IBS Patients)

**Shopify Mapping:** `sections/fgp-hero-banner.liquid` — mobile benefit panel variant

---

### Section: Mobile Comparison Table
**Node ID:** `303:12992` · **Height:** ~1200px

**Layout:**
- Full-width, horizontally scrollable table or condensed stacked layout.
- Header row + 10 feature rows. Stressbiotic col highlighted `#f6f9ea`.
- bg: `#ffffff`; table card `border-radius: 16–24px`

**Colors:** Same as desktop table. H2 `#65438a`, table cells `#f6f9ea` / `#ebebeb`

**Typography:**
- H2: Poppins SemiBold 24–28px
- Table cells: Poppins SemiBold 13–14px (condensed for mobile)

**Copy:** Same comparison data as desktop (H2: "How Stressbiotic® compares", same 10 rows)

**Shopify Mapping:** `sections/main-collection-product-grid.liquid` table — add `overflow-x: scroll` on mobile

---

### Section: Mobile Recommended For
**Node ID:** `303:13032` · **Height:** ~1400px

**Layout:**
- Single-column. H2 top. 4 benefit cards stacked vertically.
- bg: `#f8f8f8`; card bg: `#ffffff`; `border-radius: 27px`

**Colors:** Same as desktop "Who Is It For" section

**Typography:**
- H2: Poppins SemiBold 28px
- Card FOR label: Poppins Medium 12px uppercase
- Card title: Poppins SemiBold 20px
- Card body: Poppins Regular 14px

**Copy:** Same 4 cards as desktop (Busy Professionals / IBS patients / Stressed people / Sleep-troubled)

**Shopify Mapping:** `sections/fgp-products-grid.liquid` — single-column mobile layout

---

### Section: Mobile Product Cards Section
**Node ID:** `303:13122` · **Height:** ~950px

**Layout:**
- Single-column or horizontally scrollable. H2 top. 3 product cards stacked/scrollable.
- bg: `#ffffff`; card bg `#ffffff`; `border-radius: 16–24px`

**Colors:** Same as desktop related products

**Typography:**
- H2: Poppins SemiBold 24–28px
- Card name: Poppins SemiBold 18px
- Price: Poppins Regular 14–16px
- Button: Poppins SemiBold 14–16px

**Copy:** Same 3 products (Digestive Enzymes Synbiotic+/$65 · Kids Probiotic Gummies/$75 · Magnetic Pill Boxes/$16)

**Shopify Mapping:** `sections/featured-collection.liquid` — mobile: horizontal scroll row or stacked

---

### Section: Mobile Video Section
**Node ID:** `303:13174` · **Height:** ~320px

**Layout:** Full-width video card. Centered. Play button overlay. `border-radius: 24px`.

**Colors:** Card bg `#fdfbf7`; section bg `#f8f8f8`; play icon `#234092`

**Copy:** No text content (video thumbnail + play button)

**Shopify Mapping:** `sections/video.liquid` — same as desktop, mobile-responsive

---

### Section: Mobile FAQ Section
**Node ID:** `303:13178` · **Height:** ~750px

**Layout:** Single-column accordion. H2 top. 4 accordion items stacked.

**Colors:** Same as desktop FAQs. H2 `#65438a`, accordion bg `#f8f8f8`

**Typography:**
- H2: Poppins SemiBold 24–28px
- Question: Poppins SemiBold 16px
- Answer: Poppins Regular 14px

**Copy:** Same 4 FAQ items as desktop

**Shopify Mapping:** `sections/collapsible-content.liquid` — same section, mobile-responsive

---

### Section: Mobile Doctors Section
**Node ID:** `303:13204` · **Height:** ~1100px

**Layout:**
- Single-column. H2 top. 3 doctor cards stacked vertically.
- bg: `#f8f8f8`; cards: white, `border-radius: 16px`

**Colors:** Same as desktop medical reviews

**Typography:**
- H2: Poppins SemiBold 24–28px
- Doctor name: Poppins SemiBold 16–18px
- Review body: Poppins Regular 14px

**Copy:** Same 3 doctors (Dra. Nancy Conejo / Dra. Von Saalfeld / Dra. Andrea Masís)

**Shopify Mapping:** `sections/multicolumn.liquid` doctor card blocks — single-column on mobile

---

### Section: Mobile Customer Reviews Section
**Node ID:** `303:13238` · **Height:** ~1000px

**Layout:** Single-column or 2-column. H2 + aggregate rating. 4 review cards.

**Colors:** Same as desktop customer reviews

**Typography:**
- H2: Poppins SemiBold 24–28px
- Reviewer: Poppins SemiBold 16px
- Review: Poppins Regular 14px

**Copy:** Same 4 customer reviews as desktop, H2: "Loved by Customers"

**Shopify Mapping:** Same review section, mobile-responsive

---

### Section: Mobile Promo Banner (Brand Strip)
**Node ID:** `303:13279` · **Height:** ~70px

**Layout:** Full-width. bg: `#fdb921`. Tagline + hashtag + Instagram handle, same as desktop strip.

**Colors:** Background `#fdb921`; text `#234092`

**Typography:** Poppins Regular 12–14px for all text items

**Copy:** Same as desktop brand strip — "#FeelGoodWithin" · "feel.goodpharma"

**Shopify Mapping:** `sections/announcement-bar.liquid`

---

### Section: Mobile Footer
**Node ID:** `303:13296` · **Height:** ~600px

**Layout:**
- Single-column stacked footer. Logo top-center. Nav links in accordion or stacked list. Email subscribe. Copyright + payment icons bottom.
- bg: `#234092`; all text: `#ffffff`

**Colors:** Same as desktop footer

**Typography:**
- Logo: SVG (white)
- Nav links: Poppins Regular 14–15px
- Subscribe: Poppins Medium 20px / Regular 12px
- Copyright: Poppins Regular 11–12px

**Copy:** Same as desktop footer content

**Shopify Mapping:** `sections/footer.liquid` — mobile-responsive, collapsible columns

---

### Section: Mobile Sticky Add to Cart
**Node ID:** `303:13346` · **Height:** ~80px

**Layout:** Fixed bottom bar. Product info left; buttons right (or stacked for small screens).

**Colors:** Bar bg: `#f8f8f8` or white; ATC: `#144ca1` or `#f8f8f8`; BIN: `#fdb921`

**Typography:** Poppins SemiBold 14–15px `letter-spacing: 1.05px`

**Copy:** "Add to Cart" · "Buy It Now"

**Shopify Mapping:** `assets/sticky-atc.js` — same sticky bar, mobile layout variant

---

<a id="slide-menu"></a>
## 6. Mobile — SlideMenu Component
**Node ID:** `303:13351` · **Size:** 280 × 634px

**Layout:**
- Off-canvas panel slides in from left.
- FGP logo top. Nav links stacked vertically with dividers. Bottom: social icons or secondary links.
- bg: `#45bfef`

**Colors:**
- Background: `#45bfef`
- Logo: `#234092` (colored) or white
- Nav links: `#234092`
- Dividers: `rgba(255,255,255,0.2)`
- Close icon: `#234092`

**Typography:**
- Nav links: Poppins Regular 16px `line-height: 24px, letter-spacing: 0.6px`
- Active link: Poppins SemiBold 16px

**Spacing:** Link row height: `56–64px`; divider: `1px`; panel padding: `20–24px`

**Copy:**
- Nav items: "Home" · "Formulations" · "Science Behind It" · "About Us"
- Secondary: "FAQ" · "Contact Us" (optional lower section)

**Shopify Mapping:** `sections/header.liquid` drawer menu — Shopify Dawn `details` element + CSS transform slide-in

---

<a id="shopify-mapping"></a>
## 7. Shopify Section Mapping Reference

| Figma Section | Shopify Section / Snippet | Notes |
|---|---|---|
| Desktop + Mobile Header | `sections/header.liquid` | Custom bg color `#45bfef`, keep nav links, add hamburger for mobile |
| Hero 02_V2 + Hero 01_Mobile | `sections/fgp-hero-banner.liquid` | Two-column desktop, stacked mobile. Schema: heading/subheading/CTAs/pills/image |
| Hero 03_V2 + Hero 03_Mobile | `sections/fgp-hero-banner.liquid` (variant) | Symptom quiz CTA; alternate hero style |
| SlideMenu | `sections/header.liquid` drawer | Off-canvas menu, bg `#45bfef` |
| ProductInfo (D+M) | `sections/featured-product.liquid` | Full product form with subscription options |
| Info Bar (badges) | `sections/fgp-product-benefits.liquid` | 6 icon badges, `#f8f8f8` bg strip |
| Ingredients | `sections/fgp-product-benefits.liquid` | 4-col grid desktop, stacked mobile |
| How Formulations Work | `sections/fgp-hero-banner.liquid` | 4-step process layout |
| Benefit Banner | `sections/fgp-hero-banner.liquid` | Two-panel blue layout |
| Comparison Table | Custom section (static Liquid table) | Scrollable on mobile, `border-radius: 24px` card |
| Who Is It For / Recommended For | `sections/fgp-products-grid.liquid` | 4 benefit cards |
| Related Products | `sections/featured-collection.liquid` | 3 product cards |
| Video | `sections/video.liquid` | Shopify native video section |
| FAQs | `sections/collapsible-content.liquid` | Accordion with `border-radius: 20px` items |
| Doctor Reviews | `sections/multicolumn.liquid` | 3 doctor card blocks |
| Customer Reviews | `sections/multicolumn.liquid` | 4 review card blocks (or reviews app) |
| Brand Strip | `sections/announcement-bar.liquid` | bg `#fdb921`, marquee or static |
| Dosage/Shipping Accordions | Collapsible tabs in product form | Part of product page, not standalone section |
| Footer | `sections/footer.liquid` | 4 columns desktop, stacked mobile, bg `#234092` |
| Sticky ATC | `snippets/sticky-atc.liquid` + JS | Fixed bottom bar, appears on scroll past ATC |

---

## Variant Coverage Summary

| Section | Desktop | Mobile |
|---|---|---|
| Header | ✓ `303:10881` | ✓ `303:12067` |
| Hero V2 | ✓ `303:13695` | ✓ `303:13775` |
| Hero V3 (Alt) | ✓ `303:13714` | ✓ `303:13797` |
| Slide Menu | — | ✓ `303:13351` |
| Product Form | ✓ `303:11570` | ✓ `303:12787` |
| Benefit Badges | ✓ `303:11648` | — (same strip, mobile CSS) |
| Ingredients | ✓ `303:11649` | ✓ `303:12855` |
| How It Works | ✓ `303:11709` | — (same content) |
| Benefit Banner | ✓ `303:11738` | ✓ `303:12926` |
| Comparison Table | ✓ `303:11803` | ✓ `303:12992` |
| Who Is It For | ✓ `303:11843` | ✓ `303:13032` |
| Related Products | ✓ `303:11932` | ✓ `303:13122` |
| Video | ✓ `303:11996` | ✓ `303:13174` |
| FAQs | ✓ `303:12002` | ✓ `303:13178` |
| Doctor Reviews | ✓ `303:12042` | ✓ `303:13204` |
| Customer Reviews | ✓ `303:12043` | ✓ `303:13238` |
| Brand Strip | ✓ `303:12044` | ✓ `303:13279` |
| Footer | ✓ `303:12059` | ✓ `303:13296` |
| Sticky ATC | ✓ `303:12060` | ✓ `303:13346` |
| Accordions (dosage etc.) | — (within PDP) | ✓ `303:12834` |
| Product Gallery | — (within PDP) | ✓ `303:12105` |
| Quote Banner | — | Hidden `303:12920` |
