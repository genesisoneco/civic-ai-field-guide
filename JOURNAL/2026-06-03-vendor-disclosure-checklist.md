# 2026-06-03 — AI vendor disclosure checklist

## Self-assess

The last ship added a stop-rule guide for when AI should not be used. Its next practical gap was procurement and adoption: readers may agree that a system needs evidence, notice, recourse, and accountability, but still need plain questions to ask a vendor before buying or piloting. This run adds a vendor disclosure checklist that turns those safeguards into a source-backed request packet.

## Objective alignment

- Education: explains vendor disclosure in accessible language without pretending a demo is evidence.
- Better world: gives schools, workplaces, nonprofits, and public offices concrete questions that can prevent opaque, high-risk deployment.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, or manipulative monetization.
- Continuous improvement: expands the starter path from definitions and stop rules into adoption due diligence.
- Visual assets: adds a rights-safe local SVG map with title, description, alt text, and contextual caption.
- Ethical SEO: adds a descriptive URL, reader-serving title and metadata, Article JSON-LD, source trail, and homepage internal link.

## Evidence

Public content added or changed:

- `guides/vendor-disclosure-checklist.html`
- `assets/vendor-disclosure-map.svg`
- Homepage guide count and internal link in `index.html`
- Implementation plan in `docs/plans/2026-06-03-vendor-disclosure-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- U.S. Office of Management and Budget — M-24-10 on agency AI governance and risk management: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- UK Government — Guidelines for AI procurement: https://www.gov.uk/government/publications/guidelines-for-ai-procurement
- OECD — AI Principles: https://oecd.ai/en/ai-principles
- European Commission — Regulatory framework for AI: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers involved in procurement or tool evaluation need a sendable request template more than a long policy essay.
- The checklist is useful across schools, workplaces, nonprofits, and public offices without pretending to be legal or procurement advice.
- A visual “evidence trail” helps readers see vendor disclosure as a chain of practical safeguards, not a compliance ritual.

## Self-correct

Avoid making “vendor provided documentation” sound like proof of safety. The page distinguishes vendor answers from adoption readiness and tells readers to sort answers into ready-to-test, needs-limits, and stop-or-reject buckets. Future pages should keep treating disclosure as the start of evaluation, not the end.

## Self-learn

The previous stop-rule page named what must be present before AI affects people. This checklist translates those same values into procurement friction: a useful AI literacy site should help readers slow down a purchase before it becomes a harmful workflow.

## Design/backend/image/SEO improvement notes

- Design: reused the static guide style for consistency and added a scannable six-area checklist plus a copy-and-send template.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, accessibility, and maintenance.
- Image: created a local SVG asset with `<title>`, `<desc>`, semantic page alt text, and a caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking.
- Accessibility: used semantic headings, real lists, visible links, high-contrast text, non-color-only meaning, alt text, and a text template rather than an image-only checklist.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- External source reachability check returned HTTP 200 for NIST, OMB, UK Government, OECD, European Commission, and CISA URLs.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add a short public checklist for using AI in meetings without leaking sensitive information, excluding participants, or turning summaries into false records.
