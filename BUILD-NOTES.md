# Build Notes - groundlayer.co v2

**Built:** 2026-06-02
**Brief:** modules/groundlayer/design-systems/BRIEFS/groundlayer-site.md

## What changed

Replaced the entire frontend with a Bedrock-flavor single-page identifier aligned to the Groundlayer brand family system. Fresh build per the Claude Design brief.

### Files replaced
- `index.html` - Single-page identifier with logo header, hero, child brands (3-column grid), about, contact, footer. All sections separated by horizon rules.
- `privacy.html` - Holding-company-level privacy policy covering Groundlayer LLC and all operating brands. Last updated 2026-04-19.
- `terms.html` - Holding-company-level terms of service. Last updated 2026-04-19.
- `css/site.css` - Single stylesheet. Groundlayer flavor tokens, CSS Grid brands row, print styles, prefers-reduced-motion, focus rings.

### Files updated
- `assets/logo.svg` - Copied from canonical source at modules/groundlayer/design-systems/logos/groundlayer.svg.

### Files kept unchanged
- `CNAME` - Unchanged (groundlayer.co).
- `assets/favicon.svg` - Already exists, correct (lowercase "g" in Inter 700, ink on paper, thin rule).
- `robots.txt` - Already correct.
- `sitemap.xml` - Already correct. Updated lastmod to 2026-06-02.
- `llms.txt` - Already correct (AI agent overview).

### Plans directory
The `plans/` directory does not exist in the current repo. It was removed in a prior build (April 2026) - it contained a legacy SLP Web Design pricing page that belonged on simonlpaige.com, not groundlayer.co. No action needed.

## Brand authority

All design decisions derived from (read in order):
1. `modules/groundlayer/BRAND-FAMILY.md` - family skeleton
2. `modules/groundlayer/BRAND.md` - Groundlayer-specific flavor (source of truth)
3. `modules/groundlayer/design-systems/groundlayer.design.md` - design system tokens
4. `modules/groundlayer/CONTEXT.md` - legal structure

## Design decisions

- **No Source Serif 4.** Inter only, per BRAND.md: "most Groundlayer contexts are prose and structured documents."
- **No imagery.** Typography and horizontal rules only. Logo is type-only.
- **No action color.** Links use ink (#1A1A1A); hover uses secondary (#4A4A4A). Underline on hover only per design.markdown spec.
- **Three-column brand grid on desktop** (brief requirement), stacked on mobile with rule separators.
- **Hero heading at 2.4rem** as specified in the build brief.
- **Print stylesheet** included. Pages render as clean legal documents on paper.
- **No JavaScript.** Zero JS on any page.
- **No analytics.** No tracking, no third-party scripts.
- **No em dashes.** All examples use rewrites or hyphens.
- **Radius: 0px.** Groundlayer is structural, no rounding.

## Pre-commit checklist results

- Banned words: 0 hits
- Em dashes: 0 hits
- Gradients in CSS: 0 hits (0 in actual CSS, 1 in comment describing the ban)
- border-radius > 8px: 0 hits (all 0px)
- Non-Inter fonts loaded: none
- Page weight: well under 200KB per page (index.html ~4KB, privacy ~5.5KB, terms ~6KB, CSS ~6KB)
- Alt text on logo: yes ("Groundlayer LLC")
- Child brand links: simonlpaige.com, rivaldrop.com, anvilshare.ai
