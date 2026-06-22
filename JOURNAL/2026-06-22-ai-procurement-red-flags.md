# 2026-06-22 — AI procurement red flags

## Self-assess

The last ship added an AI accessibility review checklist. That improved the guide’s coverage of inclusive access before AI workflows become required. The next useful gap was procurement: a reader may understand accessibility, appeals, incidents, and risk registers, but still buy or renew a product before asking for evidence, data terms, recourse, security, exit rights, and stop rules.

## Objective alignment

- Education: explains AI procurement risk in plain language without hype, doom, or vendor-bashing.
- Better world: gives schools, workplaces, civic offices, nonprofits, and small teams practical questions to ask before AI becomes hard-to-remove infrastructure.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: extends the field guide’s information architecture from deployment safety into pre-purchase decision quality.
- Visual assets: adds a rights-safe local SVG that diagrams a procurement evidence checkpoint with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-procurement-red-flags.html`
- `assets/ai-procurement-red-flags.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-22-ai-procurement-red-flags.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — AI RMF Playbook: https://www.nist.gov/itl/ai-risk-management-framework/ai-rmf-playbook
- OECD.AI — OECD AI Principles overview: https://oecd.ai/en/ai-principles
- European Commission — AI Act regulatory framework overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- UK Government — Guidelines for AI procurement: https://www.gov.uk/government/publications/guidelines-for-ai-procurement/guidelines-for-ai-procurement
- ISO/IEC 42001:2023 — AI management system standard overview: https://www.iso.org/standard/81230.html
- W3C — Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/

Source-check note: all seven source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers searching for AI procurement help need a red-flag checklist more than a formal procurement policy template.
- The phrase “AI procurement red flags” is clear enough; future evidence may show the page should also foreground “AI vendor questions,” “AI buying checklist,” or “AI contract checklist.”
- A short written vendor question script will help buyers turn meeting impressions into auditable evidence.

## Self-correct

Avoid implying that procurement can be made safe by one checklist. The guide explicitly labels itself practical education, not legal/security/accessibility/procurement advice, and says high-stakes uses need qualified legal, privacy, security, disability-rights, domain, labor, and affected-community review.

## Self-learn

Procurement is where many AI risks become durable. The strongest reader-serving move is to ask for evidence before commitment: scope, local testing rights, data terms, recourse, accessibility, security, accountability, and exit terms should exist before the workflow becomes normal.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, two-column use-case boxes, ten-item checklist, vendor script, green signs, source list, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 12 to 13.
- Accessibility: used semantic headings, ordered/unordered lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and `git status --short --branch` showed `main` aligned with `origin/main`.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- External source reachability check returned HTTP 200 for all seven source URLs cited in the new guide.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI classroom policy starter” page: a source-backed one-page policy shape for teachers, students, and administrators deciding when AI use is allowed, limited, cited, or off-limits.
