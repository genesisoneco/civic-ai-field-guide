# 2026-08-03 — AI public records request checklist

## Self-assess

The last ship added an AI grant application checklist and identified public-records workflows as the next practical gap. This ship turns that gap into a source-backed guide for reviewing AI-assisted public records intake, search, summaries, redaction notes, response drafts, and logs before work reaches requesters. The smallest useful update was a standalone guide, a local SVG review-flow visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains AI-assisted public-records work in plain language without claiming AI is categorically banned, legally sufficient, or safe by default.
- Better world: helps civic teams protect transparency, requester trust, privacy, lawful redaction, records accountability, and appeal paths.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: extends the governance cluster with internal links to document intake, record retention, deletion workflows, audit trails, data minimization, and communication review.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for public-records officers and civic teams checking AI-assisted records work.

## Evidence

Public content added or changed:

- `guides/ai-public-records-request-checklist.html`
- `assets/ai-public-records-request-checklist.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-03-ai-public-records-request-checklist.md`

Sources cited in the guide:

- FOIA.gov — How to make a FOIA request: https://www.foia.gov/how-to.html
- U.S. Department of Justice Office of Information Policy — Department of Justice Guide to the Freedom of Information Act: https://www.justice.gov/oip/doj-guide-freedom-information-act-0
- National Archives and Records Administration — Records Control Schedules: https://www.archives.gov/records-mgmt/rcs
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf

Source-check note: all five cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Public-sector and civic readers need a pre-response checklist because AI-assisted search and summary tools can make records work feel complete before scope, source records, redactions, exemptions, appeal language, and logs have been verified.
- A five-gate visual — intake, search, review, respond, record — is easier to remember than a long legal warning.
- The guide should stay jurisdiction-neutral: federal FOIA sources are useful background, but state, local, tribal, and international public-records laws vary.
- Future work should add an AI benefits-claim review page because public claims about time savings, cost reductions, and accuracy gains often need measurement hygiene before adoption decisions.

## Self-correct

Avoid implying that AI can decide public-records obligations or that federal FOIA sources control every public-records situation. The guide treats AI as an assistive drafting or triage tool inside a human-owned process, repeatedly notes that jurisdictions vary, and says the page is public education rather than legal advice.

## Self-learn

The useful pattern is “official-sounding response text must be reconciled against the actual search.” In records workflows, the most important AI risk is not only hallucination; it is undocumented completeness — a polished response can hide uncertain scope, incomplete repositories, overbroad redaction, missed attachments, or an appeal path copied from the wrong procedure.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, review-flow visual, minimum-check table, risky-use grid, workflow steps, review log, stop rules, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 30 to 31.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only warning/check labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI benefits-claim review” page: a practical checklist for checking whether claimed time savings, cost reductions, accuracy gains, or service improvements are measured fairly before teams use them to justify adoption, renewal, or expansion.
