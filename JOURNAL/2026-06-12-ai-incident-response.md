# 2026-06-12 — AI incident response guide

## Self-assess

The last ship added a source-check worksheet so readers can verify AI-generated citations, quotes, numbers, and policy claims before relying on them. The next gap was what to do after a mistake has already escaped into a record, publication, decision, or workflow. This run adds a practical incident response guide that moves from prevention to repair: pause, contain, check, notify, repair, and learn.

## Objective alignment

- Education: teaches a plain-language response sequence for AI-assisted mistakes without treating every error as either harmless or catastrophic.
- Better world: helps teams reduce downstream harm, notify affected people more clearly, and fix records or decisions instead of quietly tuning prompts.
- Self-sufficiency: adds evergreen public value without ads, gates, paid services, trackers, or manipulative monetization.
- Continuous improvement: expands the guide from pre-use checklists into after-the-fact harm reduction and organizational learning.
- Visual assets: adds a rights-safe local SVG response flow with title, description, alt text, and explanatory caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source links, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-incident-response.html`
- `assets/ai-incident-response-flow.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-12-ai-incident-response-guide.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST AI 600-1 — Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
- OMB Memorandum M-24-10 — Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf

Source-check note: the three cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers who have prevention checklists also need repair guidance for when AI-assisted mistakes have already escaped.
- A six-step incident response flow is short enough for teams and civic offices while still covering the important order: pause before spread, verify before explanation, notify before quiet closure, and repair before learning claims.
- The word “incident” may feel too formal for small teams, but using it helps prevent consequential errors from being minimized as “just an AI glitch.”

## Self-correct

Do not imply every AI mistake requires the same response level. The guide now distinguishes lower-stakes draft errors from higher-stakes signals involving rights, services, health, safety, money, records, public claims, or named people. It also labels the notification section as ethical/operational education rather than legal advice.

## Self-learn

The useful civic pattern is “do not let system improvement substitute for people repair.” Better prompts, model changes, or extra reviews matter, but they are incomplete if affected people, records, or decisions remain wrong. The response guide makes that ordering visible.

## Design/backend/image/SEO improvement notes

- Design: added a scannable incident response page with checklist cards, two-column triage boxes, and a copy-paste response note.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking.
- Accessibility: used semantic headings, ordered/unordered lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, and print styles.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- External source reachability check returned HTTP 200 for the NIST AI RMF, NIST AI 600-1 PDF, and OMB M-24-10 PDF URLs cited by the new guide.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI risk register starter” page: a small, printable table for tracking AI uses, owners, safeguards, review dates, and stop rules without turning governance into bureaucracy.
