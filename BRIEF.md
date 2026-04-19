# groundlayer.co Frontend Refresh - Build Brief (for Claude Code subagent)

You are Claude Code. Refresh the groundlayer.co site in `~/.openclaw/workspace/groundlayer-site`. This site already exists (`index.html`, `privacy.html`, `terms.html`, `plans/`). Replace the frontend with a Bedrock-flavor single-page identifier aligned to the Groundlayer brand family system.

Deploy target: GitHub Pages (CNAME already set to groundlayer.co).

## What Groundlayer is

The Missouri holding LLC that owns Simon L. Paige Web Design, RivalDrop, and Anvilshare. The audience for this site is NOT consumers - it's lawyers, accountants, business partners, and anyone who Googled the company name after receiving a document. Read `~/.openclaw/workspace/modules/groundlayer/BRAND.md` BEFORE writing any code.

## Brand authority (READ IN ORDER)

1. `~/.openclaw/workspace/modules/groundlayer/BRAND-FAMILY.md` - family skeleton.
2. `~/.openclaw/workspace/modules/groundlayer/BRAND.md` - Groundlayer-specific flavor. Sparse, institutional, typography-first. THIS IS THE SOURCE OF TRUTH.
3. `~/.openclaw/workspace/modules/groundlayer/PIPELINE.md` - for context about what the child brands do.
4. `~/.openclaw/workspace/modules/groundlayer/CONTEXT.md` - legal structure, EIN status, sole member Simon L. Paige.

## Hard constraints (FAMILY LAW)

Same as family law. No gradients, no em dashes, no banned words, no uppercase button labels, no stock photos, no AI imagery, no emoji in UI, Lucide 1.5 stroke SVG icons, <500KB page weight, WCAG AA min / AAA body, focus rings visible.

Extra restraint for Groundlayer specifically:
- **No Source Serif 4 unless needed for a document header.** Inter is the primary face here. Groundlayer does not need display type.
- **No imagery at all.** Typography and a single thin horizontal rule.
- **No action color on main identity.** Links and buttons use ink (near-black) or secondary (mid-grey).
- **No personality performance.** This brand is deliberately the least expressive in the family.

## Banned words (zero tolerance)

unlock, leverage, seamless, delight, journey, robust, empower, transformative, innovative, best-in-class, synergy, ecosystem (unless literal), streamline, holistic, elevate, cutting-edge, unlock the potential, limited spots, now more than ever, digital transformation, book now, act fast, absolutely, wonderful, great question, of course, revolutionize, game-changer, paradigm shift, next-generation, dive in, deep dive (as noun phrase).

No em dashes. No en dashes as sentence punctuation. Hyphens or rewrites only.

## Groundlayer flavor tokens (DO NOT DEVIATE)

```css
--ink: #1A1A1A;        /* primary text, buttons, links */
--paper: #F7F5F2;      /* background */
--secondary: #4A4A4A;  /* secondary text, hover */
--rule: #C8C5C0;       /* borders, horizon lines */
--success: #2E7D52;
--error: #B03030;
```

Base rem: `16px` (family default). Inter throughout. Optional Source Serif 4 for one display element if absolutely needed (probably not).

## Voice rules

- **Neutral, competent, sparse.** Statements of fact. No metaphor. No enthusiasm.
- **No marketing language at all.** No hype. No calls to action beyond "If you're looking for X, go here."
- **No first person.** Third person institutional register. "Groundlayer LLC is a Missouri holding company."
- **Pointer rule**: if a consumer lands here, immediately tell them what Groundlayer is and point them to the right child brand. No dead ends.
- Lift sample copy from BRAND.md verbatim where it fits.

## Site structure

Current files in `~/.openclaw/workspace/groundlayer-site/`:
```
CNAME           (keep - groundlayer.co)
index.html      (REPLACE)
privacy.html    (REPLACE)
terms.html      (REPLACE)
plans/          (investigate contents - likely legacy; remove or replace)
```

Target structure:
```
groundlayer-site/
  CNAME
  index.html           # single-page identifier
  privacy.html         # holding-company-level policy covering all child brands
  terms.html           # holding-company-level terms
  css/
    site.css
  assets/
    logo.svg           # from modules/groundlayer/design-systems/logos/groundlayer.svg (copy it in)
    favicon.svg        # generate: lowercase "g" in Inter 700, ink on paper, thin rule
  BUILD-NOTES.md
```

The `plans/` directory currently under groundlayer-site - investigate it first. If it's a legacy SLP plans page that accidentally landed on this domain, delete it. If it's something else, leave it and flag in BUILD-NOTES.md.

## Page content requirements

### index.html - single-page identifier

Structure (every section separated by a 1px horizon rule):

1. **Header** (left-aligned, plain)
   - Logo wordmark (inline SVG or <img>, Inter 700 lowercase "groundlayer" with a thin rule above it - use the logo file provided).
   - No nav. The site is one page.

2. **Hero** (no display type - just Inter)
   - Large heading (Inter 700, ~2.4rem): "Groundlayer LLC"
   - Single paragraph subhead (Inter 400, 1.125rem): "Groundlayer LLC is a Missouri holding company. Its brands build websites, competitive intelligence tools, and software replacements for Kansas City small businesses."

3. **Child brands** (3-column on desktop, stacked on mobile, no cards - just text blocks with rules between)
   - **Simon L. Paige Web Design** - Custom websites for KC small businesses. Starting at $399. `simonlpaige.com`
   - **RivalDrop** - Competitive intelligence for Shopify merchants and KC local businesses. `rivaldrop.com`
   - **Anvilshare** - Software replacement studio. Replaces expensive SaaS with AI-native alternatives on customer-owned hardware. `anvilshare.ai`
   
   Each brand is a plain link. No buttons. No icons. No color accents. Just typography with the rule above and below the block.

4. **About** (single paragraph, no heading frills)
   - Lift from BRAND.md: "Groundlayer LLC is a single-member Missouri LLC founded in April 2026 by Simon L. Paige. It holds the intellectual property, contracts, and billing infrastructure for Simon L. Paige Web Design, RivalDrop, and Anvilshare. It does not sell directly to consumers."

5. **Contact** (Plain prose, no form)
   - Legal/business inquiries: `simon@groundlayer.co`
   - Mailing address: optional - include if one is listed in modules/groundlayer/CONTEXT.md; otherwise omit.

6. **Footer** (single line, Inter 400, muted)
   - "Groundlayer LLC, a Missouri limited liability company. Sole member: Simon L. Paige." + links to privacy + terms.

### privacy.html

- Holding-company-level policy covering Groundlayer LLC and all operating brands (SLP Web Design, RivalDrop, Anvilshare).
- Plain English. Read like a legal brief by someone who hates legal jargon.
- Sections: Information we collect / How we use it / How we store it / Your rights / Contact / Effective date.
- Last updated 2026-04-19.
- Voice: pure Groundlayer (sparse, institutional). No marketing.

### terms.html

- Holding-company-level terms of service.
- Plain English.
- Sections: Acceptance / Services / Payment / Intellectual property / Liability / Governing law (Missouri) / Contact.
- Last updated 2026-04-19.
- Voice: pure Groundlayer.

## CSS requirements

- Single stylesheet. CSS Grid for the 3-column brand row; Flexbox for header.
- Horizon rules: `<hr>` elements styled as 1px horizontal lines in `--rule` color, full-width within the content container.
- Max content width: 960px, centered.
- All interactive elements: keyboard focus visible, 2px outline in `--ink` with 2px offset.
- Print styles preserved (looks like a legal document on paper).
- Respect `prefers-reduced-motion`.
- No framework, no JS required for visibility.

## Pre-commit checklist

1. Grep for banned words - zero hits.
2. Grep for em dashes - zero hits.
3. Grep for "gradient" in CSS - zero hits.
4. Grep for `border-radius` values above 8px - zero hits. (Actually Groundlayer should have minimal radius - mostly 0 or 4px.)
5. No imagery beyond the logo wordmark SVG.
6. No non-Inter fonts loaded (Source Serif 4 OK if used; JetBrains Mono not needed here unless a document header uses it).
7. Page weight <200KB per page (this should be very light).
8. Real alt text on the logo.
9. Three child-brand links resolve to the correct domains.

## Deliverables

1. index.html, privacy.html, terms.html complete.
2. css/site.css complete.
3. assets/logo.svg and favicon.svg in place.
4. plans/ directory investigated, removed or flagged.
5. BUILD-NOTES.md written.
6. Single git commit: `groundlayer.co v2 - Bedrock flavor, single-page identifier, institutional register`.

## Do not

- Push or deploy.
- Run `gh` or any GitHub operations.
- Touch any file outside `~/.openclaw/workspace/groundlayer-site/`.
- Add marketing language, enthusiasm, or metaphors.
- Add imagery beyond the logo.
- Add tracking, analytics, or third-party scripts.
- Use Source Serif 4 unless the layout genuinely needs display type (it shouldn't).

## When you finish

Run this command to wake Larry:

```
openclaw system event --text "Done: groundlayer.co v2 site built locally. Ready for review." --mode now
```

Go.
