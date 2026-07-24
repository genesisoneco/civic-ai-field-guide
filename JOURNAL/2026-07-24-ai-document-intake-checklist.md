# 2026-07-24 — AI document intake checklist

## Self-assess

The last ship added an AI policy exception log and identified document intake as the next practical gap. This ship fills that gap with a source-backed checklist for deciding which documents can be uploaded into AI tools, which need reduction or review, and which should stay out. The smallest useful update was a standalone guide, a local SVG decision-flow visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains document upload risk in plain language without hype, doom, or pretending one checklist solves every legal or security issue.
- Better world: helps schools, nonprofits, civic offices, and teams reduce accidental exposure of personal, confidential, regulated, or security-sensitive information before files enter AI systems.
- Self-sufficiency: adds evergreen public value without ads, paid gates, dark patterns, tracking scripts, or exploitative monetization.
- Continuous improvement: extends the governance/privacy cluster with internal links to data minimization, retention, deletion, source checking, and exception logging.
- Visual assets: adds a rights-safe local SVG decision flow with `<title>`, `<desc>`, descriptive alt text, and caption.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for readers asking what is safe to upload into AI tools.

## Evidence

Public content added or changed:

- `guides/ai-document-intake-checklist.html`
- `assets/ai-document-intake-checklist.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-07-24-ai-document-intake-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- UK Information Commissioner’s Office — Artificial intelligence guidance: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/
- U.S. Federal Trade Commission — Protecting Personal Information: A Guide for Business: https://www.ftc.gov/business-guidance/resources/protecting-personal-information-guide-business
- OWASP — OWASP Top 10 for LLM Applications 2025: https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design

Source-check note: all six cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a practical document gate because uploading PDFs, spreadsheets, meeting notes, screenshots, and email threads is one of the fastest ways to create privacy, records, security, or confidentiality exposure.
- A sensitivity table plus “reduce before upload” pattern is more useful than only saying “do not upload sensitive data,” because real teams need alternatives.
- Future work should add an AI staff training log because policies and checklists only help when people know which rules, review duties, and stop rules apply to them.

## Self-correct

Avoid implying that redaction, de-identification, or using an approved tool automatically makes a document safe. The guide states that a checklist does not guarantee privacy, security, compliance, or accuracy; reduction is not magic anonymization; and higher-risk documents should be kept out unless approved workflows and owners exist.

## Self-learn

The useful pattern is “classify, reduce, then decide.” Many risky AI uploads happen because the upload step arrives before classification. A small intake gate can shift the workflow from convenience-first to purpose-first without requiring a large governance program.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, decision-flow visual, sensitivity table, permission checks, data-reduction tactics, prompt-injection warning, bad signs, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 26 to 27.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI staff training log” page: a lightweight record for tracking who has been trained on AI policy, privacy, accessibility, review duties, data intake, incident response, and stop rules.
