# 2026-07-15 — AI record retention schedule

## Self-assess

The last ship added an AI data minimization checklist and identified record retention as the next practical privacy/accountability layer. This ship turns that gap into a public retention schedule template for AI-related prompts, uploads, outputs, logs, evaluations, incidents, appeals, and deletion evidence.

## Objective alignment

- Education: explains AI record retention in plain language and distinguishes temporary work materials from accountability records.
- Better world: encourages shorter retention, named ownership, access limits, legal/appeal/incident hold awareness, vendor-setting alignment, and deletion evidence without keeping deleted content.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the governance/privacy cluster and updates homepage guide count, internal linking, and next-topic cards.
- Visual assets: adds a rights-safe local SVG lifecycle diagram showing create, use, review, archive/delete, and deletion evidence.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, homepage internal linking, and search-intent fit for people seeking an AI retention schedule.

## Evidence

Public content added or changed:

- `guides/ai-record-retention-schedule.html`
- `assets/ai-record-retention-schedule.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-15-ai-record-retention-schedule.md`

Sources cited in the guide:

- NIST — Privacy Framework: https://www.nist.gov/privacy-framework
- UK Information Commissioner’s Office — Storage limitation: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/data-protection-principles/a-guide-to-the-data-protection-principles/storage-limitation/
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- U.S. Office of Management and Budget — M-24-10: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- U.S. National Archives and Records Administration — Records management language for contracts: https://www.archives.gov/records-mgmt/policy/records-mgmt-language

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a category-based schedule more than exact retention periods because lawful retention windows vary across jurisdictions, sectors, contracts, public-records duties, and litigation holds.
- Teams will benefit from distinguishing final human-approved records from temporary AI drafts and raw prompts.
- Future work should add an AI deletion request workflow because retention schedules need a practical path for receiving, triaging, confirming, and documenting deletion requests.

## Self-correct

Avoid pretending a universal AI retention period exists. The guide does not prescribe exact day counts and repeatedly flags jurisdiction, sector, contract, public-records, legal-hold, appeal, incident, and rights/safety context. It also avoids saying deletion is always allowed; it explains that valid holds or records duties can override routine deletion.

## Self-learn

AI retention is easiest to explain as lifecycle design: create fewer records, keep them only while useful or required, review on a calendar, archive or delete with evidence, and avoid keeping the deleted content inside deletion proof. The highest-risk sprawl is often outside the obvious database: screenshots, exports, vendor dashboards, tickets, embeddings, copied examples, and chat histories.

## Design/backend/image/SEO improvement notes

- Design: added a scannable page with short answer, figure, first-pass checklist, retention table, practical patterns, bad signs, starter policy language, print styles, and source list.
- Backend: no backend added; static HTML remains appropriate for speed, low hosting cost, maintainability, and auditability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 22 to 23.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for 25 HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 23 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI deletion request workflow” page: a practical path for receiving, triaging, confirming, and documenting requests to remove AI-related records when deletion is allowed or required.
