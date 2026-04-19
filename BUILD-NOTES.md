# Build Notes - groundlayer.co v2

**Built:** 2026-04-19
**Branch:** refresh-bedrock-2026-04-19
**Brief:** BRIEF.md in repo root

## What changed

Replaced the entire frontend with a Bedrock-flavor single-page identifier aligned to the Groundlayer brand family system.

### Files replaced
- `index.html` - Single-page identifier with hero, child brands, about, contact, footer.
- `privacy.html` - Holding-company-level privacy policy covering all operating brands.
- `terms.html` - Holding-company-level terms of service.

### Files created
- `css/site.css` - Single stylesheet. Groundlayer flavor tokens, CSS Grid brands row, print styles, prefers-reduced-motion, focus rings.
- `assets/favicon.svg` - Lowercase "g" in Inter 700, ink on paper, thin rule.

### Files kept
- `CNAME` - Unchanged (groundlayer.co).
- `assets/logo.svg` - Unchanged (copied from modules/groundlayer/design-systems/logos/).

### Files removed
- `plans/index.html` - Legacy SLP Web Design pricing page. Used Bebas Neue, DM Sans, dark theme with green accent colors. Belonged on simonlpaige.com, not groundlayer.co. Deleted.

## Brand authority

All design decisions derived from (read in order):
1. `modules/groundlayer/BRAND-FAMILY.md` - family skeleton
2. `modules/groundlayer/BRAND.md` - Groundlayer-specific flavor (source of truth)
3. `modules/groundlayer/PIPELINE.md` - child brand context
4. `modules/groundlayer/CONTEXT.md` - legal structure

## Design decisions

- **No Source Serif 4.** Inter only, per BRAND.md: "most Groundlayer contexts are prose and structured documents."
- **No imagery.** Typography and horizontal rules only.
- **No action color.** Links use ink (#1A1A1A); hover uses secondary (#4A4A4A).
- **Three-column brand grid** on desktop (brief requirement), stacked on mobile with rule separators.
- **Print stylesheet** included. Pages render as clean legal documents on paper.
- **No JavaScript.** Zero JS on any page.
- **No analytics.** No tracking, no third-party scripts.

## Checklist results

- Banned words: 0 hits
- Em dashes: 0 hits
- Gradients in CSS: 0 hits
- border-radius > 8px: 0 hits (all 0px)
- Non-Inter fonts loaded: none
- Page weight: well under 200KB per page
- Alt text on logo: yes ("Groundlayer")
- Child brand links: simonlpaige.com, rivaldrop.com, anvilshare.ai
