# 2026-07-10 — AI public notice template

## Self-assess

The last ship added an AI system owner checklist and identified public notice as the next useful accountability layer. This ship turns ownership, appeal paths, accessibility, and audit-trail thinking into visible language people can read before or during an AI-assisted workflow.

## Objective alignment

- Education: explains what an AI notice should say in plain language, with a starter template, table, checklist, and bad signs.
- Better world: encourages transparency, human review, review/appeal paths, language access, disability access, correction, and accountable ownership.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the governance cluster and updates homepage guide count, internal linking, and next-topic cards.
- Visual assets: adds a rights-safe local SVG showing the notice connections among purpose, AI role, owner, human review, appeal/contact, language access, disability access, and correction.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, homepage internal linking, and search-intent fit for people seeking AI disclosure language.

## Evidence

Public content added or changed:

- `guides/ai-public-notice-template.html`
- `assets/ai-public-notice-template.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-10-ai-public-notice-template.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- U.S. Office of Management and Budget — M-24-10: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- European Commission — AI Act overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- UK Information Commissioner’s Office — Guidance on AI and data protection: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/
- W3C — Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need copy-pasteable notice language more than abstract transparency principles.
- Notices are most useful when paired with a real human contact path, not just a disclosure sentence.
- Language access and disability access should be part of the first notice draft, not an afterthought.
- Future work should add an AI data minimization checklist because notice is weaker when workflows collect or retain more personal data than needed.

## Self-correct

Avoid implying that a notice alone makes an AI workflow acceptable or lawful. The guide states that notice is not a magic compliance shield, that duties vary by context, and that high-stakes workflows need meaningful review, correction, and governance. It also avoids claiming the EU AI Act, OMB policy, ICO guidance, or WCAG applies universally to every reader.

## Self-learn

The most useful notice pattern is a sentence that names the AI use and then immediately gives people agency: what it affects, who owns it, and how to reach a human for review, correction, language access, disability access, or a non-AI route. Transparency becomes more practical when it is connected to a next step.

## Design/backend/image/SEO improvement notes

- Design: added a scannable page with short answer, diagram, when-to-notice checklist, starter language, field table, accessibility section, bad signs, print-friendly checklist, and source list.
- Backend: no backend added; static HTML remains appropriate for speed, low hosting cost, maintainability, and auditability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 20 to 21.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 21 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI data minimization checklist” page: a practical guide for collecting less data, retaining it for less time, avoiding unnecessary sensitive information, and making privacy-preserving defaults part of AI workflow design.
