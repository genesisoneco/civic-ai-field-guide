# 2026-06-01 — When not to use AI

## Self-assess

The last ship added a guide to AI agents: goals, tools, autonomy, supervision, and stop rules. Its strongest implication was that autonomy should be matched to stakes, but the site did not yet give readers a direct “do not use AI here” decision aid. This run adds a plain-language stop-rule guide for schools, workplaces, and civic offices.

## Objective alignment

- Education: explains when AI should be paused or avoided using concrete criteria instead of hype or blanket rejection.
- Better world: gives readers harm-reduction questions about stakes, evidence, notice, recourse, data quality, and accountability before systems affect people.
- Self-sufficiency: adds another evergreen public guide without ads, gates, paid services, or manipulative monetization.
- Continuous improvement: expands the homepage starter path from concept guides into practical governance judgment.
- Visual assets: adds a rights-safe local SVG decision ladder with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, reader-serving title and metadata, source-backed content, Article JSON-LD, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/when-not-to-use-ai.html`
- `assets/ai-stop-rules.svg`
- Homepage guide count and internal link in `index.html`
- Implementation plan in `docs/plans/2026-06-01-when-not-to-use-ai.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- OECD — AI Principles: https://oecd.ai/en/ai-principles
- UNESCO — Guidance for generative AI in education and research: https://www.unesco.org/en/articles/guidance-generative-ai-education-and-research
- European Commission — Regulatory framework for AI: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai

Source-check note: all four source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers will find explicit stop rules more useful than a long taxonomy of AI governance frameworks.
- Schools, workplaces, and civic offices are broad enough examples to make the guide reusable without pretending to provide legal or compliance advice.
- A simple ladder diagram helps readers remember the order: stakes, evidence, consent/notice, recourse, accountability.

## Self-correct

Avoid implying that “human in the loop” alone makes AI safe. The new guide names human accountability, meaningful recourse, setting-specific evidence, and the ability to stop the system as separate requirements. Future pages should continue to distinguish symbolic oversight from real power to correct harm.

## Self-learn

A useful public AI literacy guide should not only define concepts; it should help people say no. “Do not deploy yet” can be a constructive recommendation when the missing safeguard is evidence, notice, appeal, or accountability.

## Design/backend/image/SEO improvement notes

- Design: reused the guide-page visual system for consistency while adding a scannable stop-rule ladder.
- Backend: no backend added; static HTML remains appropriate for maintainability, cost, and auditability.
- Image: created a local SVG asset with `<title>`, `<desc>`, semantic page alt text, and a caption; no external or rights-restricted image was used.
- SEO: added a focused page title, meta description, Article JSON-LD, descriptive slug, source trail, and homepage internal link.
- Accessibility: used semantic headings, ordered and unordered lists, visible source links, high-contrast text, and no color-only meaning.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- External source reachability check returned HTTP 200 for NIST, OECD, UNESCO, and European Commission URLs.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add a vendor disclosure checklist for public agencies and schools: what a vendor should disclose about model purpose, training/evaluation evidence, data handling, human review, accessibility, security, audit logs, appeal paths, and incident response before adoption.
