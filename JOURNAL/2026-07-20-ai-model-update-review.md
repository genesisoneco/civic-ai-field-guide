# 2026-07-20 — AI model update review

## Self-assess

The last ship added an AI deletion request workflow and named model update review as the next practical gap. This ship addresses the quieter risk that AI systems change after approval: a vendor updates a model, turns on a feature, changes retention settings, or a team edits a prompt and the old risk review no longer matches the actual workflow.

## Objective alignment

- Education: explains model update review in plain language as a proportional change-control checkpoint, not a mystical audit or a blanket freeze on improvements.
- Better world: helps teams catch changed error patterns, privacy exposure, accessibility issues, notice gaps, retention/deletion mismatches, staff-training needs, and rollback decisions before people are harmed.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the governance/privacy/evaluation cluster with internal links to vendor disclosure, accessibility, evaluation evidence, data minimization, public notice, retention, deletion, and incident response pages.
- Visual assets: adds a rights-safe local SVG review-loop diagram with title, description, semantic alt text, and caption.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, source-backed headings, homepage internal linking, and search-intent fit for people responsible for AI change control.

## Evidence

Public content added or changed:

- `guides/ai-model-update-review.html`
- `assets/ai-model-update-review.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-20-ai-model-update-review.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
- U.S. Office of Management and Budget — M-24-10: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- OWASP — Top 10 for Large Language Model Applications: https://owasp.org/www-project-top-10-for-large-language-model-applications/
- UK Information Commissioner’s Office — Artificial intelligence guidance: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers responsible for civic, school, nonprofit, workplace, or public-service AI systems need a lightweight review checklist more than a heavyweight model-audit framework.
- Vendor update notices are easy to miss or under-interpret, so the useful public guidance is to connect update notices to local tests, public promises, records practices, and monitoring.
- Future work should add an AI policy exception log because teams also need a way to record temporary deviations from policy without normalizing silent exceptions.

## Self-correct

Avoid implying that every model update is bad or that all changes require the same level of review. The guide frames review as proportional: a small internal prompt fix may need a quick log entry, while a model swap in a higher-impact workflow may require renewed testing, notice updates, records review, and approval. It also avoids claiming that local tests prove safety; they are evidence for a limited use case.

## Self-learn

A practical AI update review is less about the model name and more about changed promises. If behavior, data handling, access, retention, deletion, notices, appeals, or human review changes, the system people rely on has changed even if the product name stays the same.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, review-loop figure, trigger checklist, comparison table, regression-test checklist, control/update grid, monitoring section, warning signs, starter change-log language, print styles, and source list.
- Backend: no backend added; static HTML remains appropriate for speed, low hosting cost, maintainability, accessibility, and auditability.
- Image: created a local SVG with `<title>`, `<desc>`, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 24 to 25.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 25 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI policy exception log” page: a simple log for documenting approved exceptions, expiration dates, owners, safeguards, and review dates when AI policies cannot be followed exactly.
