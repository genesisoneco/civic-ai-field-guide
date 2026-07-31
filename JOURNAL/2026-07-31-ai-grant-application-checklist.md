# 2026-07-31 — AI grant application checklist

## Self-assess

The last ship added an AI communication review checklist and identified AI-assisted grant writing as the next practical gap. This ship turns that gap into a source-backed, printable guide for reviewing AI-assisted grant applications before teams submit narratives, budgets, evidence claims, partner commitments, evaluation plans, or compliance language. The smallest useful update was a standalone guide, a local SVG review-gates visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains grant-draft review in plain language without claiming AI grant writing is automatically fraudulent, safe, compliant, or forbidden.
- Better world: helps nonprofits, schools, civic teams, and community organizations avoid unsupported claims, budget mismatches, unapproved partner promises, privacy exposure, and careless compliance language.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: extends the practical governance cluster with internal links to source checking, communication review, document intake, data minimization, audit trails, and risk registers.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for teams looking for an AI grant checklist or AI-assisted grant application review.

## Evidence

Public content added or changed:

- `guides/ai-grant-application-checklist.html`
- `assets/ai-grant-application-checklist.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-07-31-ai-grant-application-checklist.md`

Sources cited in the guide:

- eCFR — 2 CFR Part 200, Uniform Administrative Requirements, Cost Principles, and Audit Requirements for Federal Awards: https://www.ecfr.gov/current/title-2/subtitle-A/chapter-II/part-200
- Grants.gov — Workspace Overview: https://www.grants.gov/applicants/workspace-overview
- U.S. Department of Justice — The False Claims Act: https://www.justice.gov/civil/false-claims-act
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- PlainLanguage.gov — Federal plain language guidelines: https://www.plainlanguage.gov/guidelines/

Source-check note: all six cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a pre-submission grant checklist because AI-assisted drafting can make proposal language look coherent before evidence, budget alignment, commitments, and compliance have been checked.
- A six-gate visual — funder fit, evidence, budget, promises, compliance, submit/revise — is easier to remember than a long warning paragraph.
- Public-interest teams will benefit from internal AI-use sign-off language that documents human review without exposing sensitive prompts or unnecessary private records.
- Future work should add an AI public records request checklist because AI-assisted search, summarization, and redaction notes can introduce legal, privacy, transparency, and trust risks.

## Self-correct

Avoid implying that using AI in grant drafting is itself fraud or noncompliance. The guide treats AI as a drafting aid that can be used carefully, while emphasizing that the submitting organization remains responsible for eligibility, evidence, numbers, commitments, records, and final sign-off. It also explicitly says the page is public education, not legal, accounting, grant-management, or compliance advice.

## Self-learn

The useful pattern is “persuasive text must be reconciled against commitments.” In grant workflows, the most important AI risk is not just hallucinated citations; it is polished coherence across sections that may actually disagree: budget, timeline, partner letters, evaluation plan, and compliance forms.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, review-gates visual, minimum-check table, risky-section grid, workflow steps, sign-off log, stop rules, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 29 to 30.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only warning/check labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI public records request checklist” page: a practical review for AI-assisted search, summaries, redaction notes, and response drafts before public-records work reaches requesters or disclosure logs.
