# 2026-07-13 — AI data minimization checklist

## Self-assess

The last ship added a public AI notice template and identified data minimization as the next useful accountability layer. This ship turns that privacy gap into a practical checklist for reducing personal-data exposure before AI touches a workflow.

## Objective alignment

- Education: explains data minimization in plain language and shows where AI workflows can accidentally retain or expose personal data.
- Better world: encourages collection limits, redaction, short retention, access boundaries, exception logs, deletion review, and accountable ownership.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the governance/privacy cluster and updates homepage guide count, internal linking, and next-topic cards.
- Visual assets: adds a rights-safe local SVG funnel showing purpose, necessary fields, redaction/protection, retention/access, and deletion review.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, homepage internal linking, and search-intent fit for people seeking AI privacy/data minimization guidance.

## Evidence

Public content added or changed:

- `guides/ai-data-minimization-checklist.html`
- `assets/ai-data-minimization-checklist.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-13-ai-data-minimization-checklist.md`

Sources cited in the guide:

- NIST — Privacy Framework: https://www.nist.gov/privacy-framework
- UK Information Commissioner’s Office — Data minimisation: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-protection-principles/a-guide-to-the-data-protection-principles/data-minimisation/
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- U.S. Office of Management and Budget — M-24-10: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- W3C — Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need field-level privacy prompts more than abstract privacy principles.
- Teams will find a “where to minimize” table useful because AI privacy risk often hides in prompts, uploads, logs, outputs, and vendor settings.
- Future work should add an AI record retention schedule because minimization depends on concrete deletion and review timing.

## Self-correct

Avoid implying that data minimization alone makes an AI workflow lawful, fair, or safe. The guide says it is not legal advice, names jurisdiction/context limits, and frames minimization as one risk-reduction habit rather than a universal compliance shield. It also avoids claiming the NIST Privacy Framework, ICO guidance, NIST AI RMF, OMB policy, or WCAG applies identically to every reader.

## Self-learn

Data minimization becomes more usable when it is expressed as a workflow map: purpose, fields, prompts, uploads, outputs, logs, training/tuning reuse, vendor sharing, access, retention, and deletion. The strongest plain-language habit is “start with no personal data, then justify each field that must be added.”

## Design/backend/image/SEO improvement notes

- Design: added a scannable page with short answer, figure, first-pass checklist, table, practical patterns, bad signs, starter policy language, print-friendly styles, and source list.
- Backend: no backend added; static HTML remains appropriate for speed, low hosting cost, maintainability, and auditability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 21 to 22.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 22 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI record retention schedule” page: a practical guide for deciding how long prompts, uploads, outputs, logs, evaluations, audit trails, incidents, appeals, and correction records should be kept or reviewed.
