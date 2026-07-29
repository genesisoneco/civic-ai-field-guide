# 2026-07-29 — AI communication review checklist

## Self-assess

The last ship added an AI staff training log and identified AI-assisted public communication as the next practical gap. This ship turns that gap into a source-backed, printable guide for reviewing AI-assisted notices, emails, web pages, translations, captions, letters, scripts, social posts, and public statements before they reach people. The smallest useful update was a standalone guide, a local SVG review-flow visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains AI-assisted communication review in plain language without claiming that AI writing is inherently safe, unsafe, objective, or compliant.
- Better world: helps schools, nonprofits, civic offices, and teams prevent real communication harms: wrong deadlines, invented facts, inaccessible content, poor translation, privacy leaks, missing human contact paths, and unclear public obligations.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: extends the governance/privacy/accessibility/language-access cluster with internal links to source checking, consent and disclosure, accessibility review, translation and language access, public notices, incident response, data minimization, and staff training.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for teams looking for an AI communication checklist, AI public message review, or AI-assisted public notice review.

## Evidence

Public content added or changed:

- `guides/ai-communication-review-checklist.html`
- `assets/ai-communication-review-checklist.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-07-29-ai-communication-review-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- White House Office of Management and Budget — M-24-10: Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- PlainLanguage.gov — Federal plain language guidelines: https://www.plainlanguage.gov/guidelines/
- W3C — Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/
- U.S. Department of Justice — Guidance on Web Accessibility and the ADA: https://www.ada.gov/resources/web-guidance/
- LEP.gov — Language access planning: https://www.lep.gov/language-access-planning

Source-check note: all seven cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a pre-publication communication checklist because AI-assisted writing tools can make drafts look finished before facts, access, privacy, language, rights, and ownership have been checked.
- A purpose/facts/people/access/privacy/publish-or-pause flow is easier to remember than a long policy paragraph.
- Public-sector and civic readers will benefit from starter sign-off language that records AI use without preserving unnecessary sensitive prompt details.
- Future work should add an AI grant application checklist because AI-assisted grant writing can create unsupported evidence claims, inflated community promises, budget inconsistencies, and compliance risks.

## Self-correct

Avoid implying that AI disclosure alone makes a message trustworthy. The guide treats disclosure as one decision inside a broader review process, not a substitute for factual, accessibility, language-access, privacy, and accountability checks. It also avoids claiming that every AI-assisted message requires public disclosure, because requirements depend on context and policy.

## Self-learn

The useful pattern is “public copy needs accountable review.” The biggest risk is not merely that AI writes awkward sentences; it is that fluent public communication can carry wrong facts, missing exceptions, inaccessible formats, or unclear appeal paths into real people’s decisions.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, review-flow visual, minimum-check table, high-risk message grid, workflow steps, sign-off log, stop rules, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 28 to 29.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only warning/check labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the seven source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI grant application checklist” page: a practical review for AI-assisted grant drafts before teams submit budgets, evidence claims, community promises, partner descriptions, or compliance language.
