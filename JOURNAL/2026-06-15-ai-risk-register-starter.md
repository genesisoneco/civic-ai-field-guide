# 2026-06-15 — AI risk register starter

## Self-assess

The last ship added an AI incident response guide for mistakes that already reached people, records, publications, decisions, or workflows. The next gap was a lighter prevention-and-visibility tool: many teams adopt multiple AI tools before anyone can answer what is in use, who owns each use, what safeguards exist, and when to stop. This run adds a practical AI risk register starter that turns that invisible inventory into a small, maintainable table.

## Objective alignment

- Education: explains risk registers in plain language without requiring readers to know governance jargon.
- Better world: helps teams name owners, affected people or records, safeguards, review dates, and stop rules before AI risks become normalized or forgotten.
- Self-sufficiency: adds evergreen public value without ads, gates, trackers, paid services, or fear-based monetization.
- Continuous improvement: expands the guide from one-off checklists into lightweight operational governance.
- Visual assets: adds a rights-safe local SVG loop with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-risk-register-starter.html`
- `assets/ai-risk-register-loop.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-15-ai-risk-register-starter.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST AI 100-1 — Artificial Intelligence Risk Management Framework: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- ISO — ISO/IEC 42001 Artificial intelligence management system overview: https://www.iso.org/standard/81230.html
- European Commission High-Level Expert Group — Ethics Guidelines for Trustworthy AI: https://digital-strategy.ec.europa.eu/en/library/ethics-guidelines-trustworthy-ai

Source-check note: the four cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Small teams need a register template that is closer to a maintained spreadsheet than a formal governance program.
- Readers will understand “owner” more readily than abstract accountability language, especially when the guide defines owner as the role that can pause, fix, notify, or retire a use.
- A six-column template is enough to start without causing abandonment from too many fields.

## Self-correct

Avoid implying that a simple register is sufficient for high-stakes AI use. The guide now says the starter register is a doorway, not a substitute, for deeper review when AI affects rights, benefits, services, education, employment, housing, health, safety, credit, legal status, or other consequential decisions.

## Self-learn

The useful pattern is “governance as shared memory.” A lightweight register should not exist to prove sophistication; it should help people see what AI is being used, who can stop it, and what evidence would trigger review or retirement.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with cards, a horizontally scrollable table, mobile-friendly sections, print styles, and a warning against decorative paperwork.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking.
- Accessibility: used semantic headings, ordered/unordered lists, table headers, an accessible scroll region label, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, and print styles.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- External source reachability check returned HTTP 200 for the NIST AI RMF, NIST AI 100-1 PDF, ISO/IEC 42001 overview, and European Commission trustworthy AI ethics guideline URLs cited by the new guide.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI appeal path checklist” page: a practical guide for helping people question, correct, or challenge AI-assisted decisions that affect them.
