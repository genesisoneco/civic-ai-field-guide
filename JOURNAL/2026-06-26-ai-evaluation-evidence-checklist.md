# 2026-06-26 — AI evaluation evidence checklist

## Self-assess

The last ship added an AI classroom policy starter. That improved classroom expectations, but the project still needed a practical bridge from “AI sounds useful” to “what evidence would justify relying on it?” This ship adds a source-backed checklist for asking about purpose, baselines, local testing, failure cases, monitoring, and stop rules before AI becomes normal workflow.

## Objective alignment

- Education: explains AI evaluation evidence in plain language without hype, doom, or technical gatekeeping.
- Better world: gives schools, workplaces, nonprofits, public offices, and small teams a concrete way to slow down overreliance and ask for inspectable evidence before harm occurs.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the guide’s information architecture from policies and procurement into evaluation practice.
- Visual assets: adds a rights-safe local SVG that diagrams the evidence path, with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-evaluation-evidence-checklist.html`
- `assets/ai-evaluation-evidence-checklist.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-26-ai-evaluation-evidence-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — AI RMF Playbook: https://www.nist.gov/itl/ai-risk-management-framework/ai-rmf-playbook
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- OECD.AI — OECD AI Principles overview: https://oecd.ai/en/ai-principles
- W3C WAI — Evaluating Web Accessibility Overview: https://www.w3.org/WAI/test-evaluate/
- European Commission — AI Act regulatory framework overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- UK Government — Algorithmic Transparency Recording Standard Hub: https://www.gov.uk/government/collections/algorithmic-transparency-recording-standard-hub

Source-check note: all seven source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a short evidence checklist more than a technical evaluation methodology.
- The “purpose → tests → results → failures → monitoring → decision” visual path will help non-specialists ask better questions in meetings.
- The minimum evidence bundle table is concrete enough for procurement, pilots, and internal AI adoption without pretending to be legal or statistical advice.
- Future work should add a dedicated guide on AI detector limits and fair process, because the classroom policy page named detector caution and this page reinforces evidence discipline.

## Self-correct

Avoid implying that a checklist can certify an AI system as safe. The guide frames evaluation as evidence for limited, contextual decisions and repeatedly names high-stakes uses as needing qualified domain, legal, privacy, security, accessibility, labor, and affected-community review.

## Self-learn

Evaluation guidance becomes more usable when it asks for ordinary artifacts — scope statements, test examples, baselines, failure cases, recourse paths, monitoring owners, and stop rules — instead of abstract “trustworthy AI” language alone. Broad frameworks are most useful to readers when converted into meeting questions and evidence bundles.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, use cases, seven checks, evidence table, meeting script, warning signs, source list, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 14 to 15.
- Accessibility: used semantic headings, ordered/unordered lists, a data table with headers, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and `git status --short --branch` showed `main` aligned with `origin/main`.
- Source reachability check returned HTTP 200 for all seven source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI detector limits and fair process” page: a source-backed guide for why AI detectors require caution, what evidence is too weak for accusations, and how schools or teams can handle suspected AI use with fair human review.
