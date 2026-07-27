# 2026-07-27 — AI staff training log

## Self-assess

The last ship added an AI document intake checklist and identified staff training records as the next practical gap. This ship turns that gap into a source-backed, printable guide for tracking who has been trained on which AI rules, for which workflow, with what evidence, and when retraining is due. The smallest useful update was a standalone guide, a local SVG training-cycle visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains AI training records in plain language without pretending a log proves safety, legality, fairness, or accessibility.
- Better world: helps schools, nonprofits, civic offices, and teams notice training gaps before people upload sensitive data, rely on unchecked output, miss accessibility duties, or fail to pause after an incident.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: extends the governance/privacy operations cluster with internal links to document intake, data minimization, source checking, accessibility review, incident response, model-update review, and system ownership.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for teams looking for an AI staff training log or training record template.

## Evidence

Public content added or changed:

- `guides/ai-staff-training-log.html`
- `assets/ai-staff-training-log.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-07-27-ai-staff-training-log.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- White House Office of Management and Budget — M-24-10: Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design
- U.S. Federal Trade Commission — Protecting Personal Information: A Guide for Business: https://www.ftc.gov/business-guidance/resources/protecting-personal-information-guide-business
- W3C — Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/
- U.S. Department of Justice — Guidance on Web Accessibility and the ADA: https://www.ada.gov/resources/web-guidance/

Source-check note: all seven cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a lightweight AI training log because policies, checklists, and owner assignments fail when staff do not know which rules apply to their actual workflows.
- A role/workflow/topic/evidence/refresh-trigger template is more useful than a generic “training complete” checkbox.
- Scenario checks are likely to improve practical use because they test decisions people actually face: upload, reduce, cite, disclose, pause, escalate, or keep out.
- Future work should add an AI communication review checklist because AI-assisted public copy can create accuracy, accessibility, language-access, privacy, and trust problems before publication.

## Self-correct

Avoid implying that training records transfer responsibility from the organization to individual staff. The guide frames the log as an accountability and improvement tool, not a blame file. It also warns against collecting unnecessary personnel details in the log.

## Self-learn

The useful pattern is “scope, evidence, refresh.” AI training gets weak when it is detached from real tool permissions and real data classes. A training log should say what the person is allowed to do, what training evidence exists, and what change triggers retraining.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, training-cycle visual, minimum-field table, topic grid, starter template, scenario checks, bad signs, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 27 to 28.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the seven source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI communication review checklist” page: a pre-publication check for AI-assisted notices, emails, web pages, translations, captions, and public statements before they reach people.
