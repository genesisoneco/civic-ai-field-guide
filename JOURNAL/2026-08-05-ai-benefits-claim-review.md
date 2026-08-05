# 2026-08-05 — AI benefits-claim review

## Self-assess

The last ship added an AI public records request checklist and named benefits-claim review as the next practical gap. This ship turns that gap into a source-backed guide for checking whether promised AI time savings, cost reductions, accuracy gains, or service improvements are measured fairly before adoption, renewal, expansion, public announcements, or budget decisions. The smallest useful update was a standalone guide, a rights-safe local SVG measurement-loop visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains how to question AI benefit claims in plain language without implying that AI is useless or automatically beneficial.
- Better world: helps civic teams avoid decisions based on unsupported vendor claims, cherry-picked pilots, hidden costs, or speed metrics that ignore quality and affected people.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the evaluation/procurement cluster with internal links to claim-checking, evaluation evidence, procurement red flags, risk registers, model update review, and communication review.
- Visual assets: adds a local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for public-sector teams evaluating AI performance claims.

## Evidence

Public content added or changed:

- `guides/ai-benefits-claim-review.html`
- `assets/ai-benefits-claim-review.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-05-ai-benefits-claim-review.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- Federal Trade Commission — Keep your AI claims in check: https://www.ftc.gov/business-guidance/blog/keep-your-ai-claims-check
- Federal Trade Commission — FTC announces crackdown on deceptive AI claims and schemes: https://www.ftc.gov/news-events/news/press-releases/2024/09/ftc-announces-crackdown-deceptive-ai-claims-schemes

Source-check note: all four cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Civic readers need a dedicated page for benefit claims because “AI saves time” and “AI improves service” claims often reach budget and renewal discussions before measurement method, baseline, hidden costs, and quality tradeoffs are visible.
- A five-stage visual — claim, baseline, evidence, tradeoffs, decision — is a memorable alternative to either accepting or rejecting AI claims reflexively.
- FTC business guidance is relevant as public education for claim discipline, but the guide should not imply every civic AI claim is a consumer-advertising violation.
- Future work should add AI pilot exit criteria so teams can decide what to do after a measured pilot rather than letting pilots drift into default adoption.

## Self-correct

Avoid treating benefits skepticism as anti-AI posture. The guide says to measure the whole workflow, not to block every benefit claim. It distinguishes vendor marketing, anecdotes, dashboards, pilots, and operational reviews by evidence strength, and it asks for local validation rather than assuming public sources can determine local outcomes.

## Self-learn

The useful pattern is “count where the work moved.” Many AI benefit claims look strong when they count draft-generation speed but weaker when human review, correction, training, support, accessibility, privacy/security review, procurement effort, incidents, appeals, and public trust are included. A fair review does not merely ask whether a tool works; it asks who gains, who pays, and what changed in the real workflow.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, measurement-loop visual, minimum-check table, evidence-strength table, workflow steps, review log, stop rules, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 31 to 32.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only warning/check labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the four source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Repository inspection found no package manifest, Makefile, or TOML build configuration, so no full site build command was available or run.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths.

## Next move

Add an “AI pilot exit criteria” page: a practical checklist for deciding whether a pilot should expand, narrow, pause, or stop after evidence review, with clear thresholds for quality, workload, risk, accessibility, user feedback, and remeasurement.
