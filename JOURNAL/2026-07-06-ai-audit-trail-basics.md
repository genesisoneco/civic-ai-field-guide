# 2026-07-06 — AI audit trail basics

## Self-assess

The last ship added an AI consent and disclosure guide. Its next-move note identified audit trails because consent, disclosure, appeals, and incident response become weak if nobody can reconstruct what AI did, what humans reviewed, and what was corrected. This ship follows that thread with a practical, source-backed guide focused on minimum useful records and data minimization.

## Objective alignment

- Education: explains AI audit trails in plain language for schools, workplaces, public offices, nonprofits, newsrooms, and community teams.
- Better world: encourages reviewable records, appeal support, incident learning, human accountability, privacy guardrails, and safer correction loops.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the guide’s accountability cluster and updates homepage guide count and internal linking.
- Visual assets: adds a rights-safe local SVG that diagrams a record-review-correct loop, with SVG title/description, image alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-audit-trail-basics.html`
- `assets/ai-audit-trail-basics.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-06-ai-audit-trail-basics.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- NIST — Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile (NIST AI 600-1): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
- European Commission — AI Act overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- UK Information Commissioner’s Office — Guidance on AI and data protection: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/

Source-check note: all five source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a small set of record fields more than a formal audit framework, especially when they are trying to start responsible practice without a compliance department.
- The privacy warning is important: many teams may over-record prompts, transcripts, or personal details while under-recording human review, outcome, appeals, and corrections.
- A loop diagram is more useful than a filing-cabinet metaphor because audit trails should feed learning, not just storage.
- Future work should add an AI system owner checklist because audit trails only help when someone has authority to pause, correct, and answer for a workflow.

## Self-correct

Avoid implying that more records are always better. The guide explicitly tells teams not to keep raw sensitive inputs, credentials, private logs, or unnecessary personal details by default. It frames recordkeeping as public-interest guidance, not legal advice, and notes that high-stakes uses need stronger review than a starter template.

## Self-learn

Audit trail guidance is clearest when it starts from reconstructability and privacy together: can a responsible person determine what happened, and did the organization avoid creating a new risk by hoarding sensitive data? The strongest starter pattern is purpose → system → input category → output role → human review → outcome → appeal or incident → correction.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, comparison boxes, data table, starter language, incident/appeal fields, bad-sign list, checklist, sources, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 18 to 19.
- Accessibility: used semantic headings, lists, a data table with headers, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 19 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI system owner checklist” page: a lightweight guide for naming the accountable owner of an AI workflow, who can pause it, who handles appeals and incidents, what evidence they must maintain, and when ownership must be reviewed after vendor, model, policy, or workflow changes.
