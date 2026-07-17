# 2026-07-17 — AI deletion request workflow

## Self-assess

The last ship added an AI record retention schedule and named deletion requests as the next practical gap. This ship turns that gap into a public workflow for handling AI-related deletion requests without pretending deletion is always immediate, universal, or legally simple.

## Objective alignment

- Education: explains deletion request handling in plain language and separates intake, triage, system search, vendor confirmation, and evidence logging.
- Better world: encourages less data sprawl, clearer requester communication, vendor follow-through, exception review, and deletion evidence that does not recreate the privacy risk.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the governance/privacy cluster and updates homepage guide count, internal linking, and next-topic cards.
- Visual assets: adds a rights-safe local SVG workflow diagram with title, description, semantic alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, homepage internal linking, and search-intent fit for people seeking an AI deletion request process.

## Evidence

Public content added or changed:

- `guides/ai-deletion-request-workflow.html`
- `assets/ai-deletion-request-workflow.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-17-ai-deletion-request-workflow.md`

Sources cited in the guide:

- UK Information Commissioner’s Office — Right to erasure: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/individual-rights/individual-rights/right-to-erasure/
- NIST — Privacy Framework: https://www.nist.gov/privacy-framework
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- U.S. Office of Management and Budget — M-24-10: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- U.S. National Archives and Records Administration — Records management language for contracts: https://www.archives.gov/records-mgmt/policy/records-mgmt-language

Source-check note: all five source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a workflow more than a legal taxonomy because deletion obligations vary across jurisdictions, sectors, vendors, contracts, and public-records duties.
- Teams will benefit from a “check every likely AI record location” section because AI-related data often persists outside the obvious application database.
- Future work should add an AI model update review checklist because deletion and retention promises can change when vendors alter logging, training, privacy, model, or feature behavior.

## Self-correct

Avoid implying a universal right to deletion or a universal duty to delete. The guide repeatedly says deletion is not always absolute and names exceptions such as legal holds, public-records obligations, audits, active incidents, appeals, security logs, safety reviews, and vendor retention limits. It also cautions against collecting extra sensitive identity proof during intake.

## Self-learn

AI deletion is best explained as controlled reduction, not a single button. The useful pattern is: receive the request, verify only what is necessary, map all record locations, check retention exceptions, delete/restrict/anonymize where appropriate, confirm vendor action, and retain only minimal metadata as proof.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, workflow figure, checklist sections, triage table, system-location grid, warning signs, starter intake language, print styles, and source list.
- Backend: no backend added; static HTML remains appropriate for speed, low hosting cost, maintainability, accessibility, and auditability.
- Image: created a local SVG with `<title>`, `<desc>`, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 23 to 24.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for 26 HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 24 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI model update review” page: a lightweight review checklist for checking whether a vendor model change, feature rollout, or policy update affects risk, notices, testing, retention, deletion, staff training, or public communication.
