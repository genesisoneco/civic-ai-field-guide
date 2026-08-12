# 2026-08-12 — AI sunset plan starter

## Self-assess

The last ship added an AI renewal decision checklist and identified the next practical gap: what to do when an AI workflow should pause, end, be replaced, or archive. This ship turns that gap into a source-backed guide for controlled AI offboarding. The smallest useful update was a standalone sunset plan guide, a local SVG shutdown-sequence visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains AI sunset planning in plain language without treating shutdown as failure or treating automation as permanent once adopted.
- Better world: helps civic teams avoid abandoned users, missing records, unresolved vendor data, dormant credentials, broken public notices, and hidden continuity failures.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the lifecycle governance cluster by linking renewal review, pilot exit criteria, record retention, deletion workflows, risk registers, public notices, and appeal paths.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated guide count, and search-intent fit for teams planning AI offboarding.

## Evidence

Public content added or changed:

- `guides/ai-sunset-plan-starter.html`
- `assets/ai-sunset-plan-starter.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-12-ai-sunset-plan-starter.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- U.S. National Archives and Records Administration — Records scheduling: https://www.archives.gov/records-mgmt/scheduling
- U.S. National Archives and Records Administration — General Records Schedules: https://www.archives.gov/records-mgmt/grs
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design
- Federal Trade Commission — Data Breach Response: A Guide for Business: https://www.ftc.gov/business-guidance/resources/data-breach-response-guide-business

Source-check note: all six cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Civic readers need a dedicated sunset page because renewal, pilot, retention, deletion, and public-notice pages do not by themselves provide a complete offboarding sequence.
- A six-step sequence — decide, freeze, preserve, transition, dispose, review — is memorable enough for meetings and detailed enough to prevent common shutdown gaps.
- NARA records-scheduling sources are useful for public-sector recordkeeping concepts, but the guide should not imply federal schedules govern every local, state, school, nonprofit, or private workflow.
- The FTC data-breach response source is relevant as practical data-handling caution, but the guide correctly labels it as not legal advice and avoids implying every AI sunset is a breach response.

## Self-correct

Avoid implying that ending an AI workflow is always the safest or most ethical choice. The guide warns that shutdown should pause if turning the system off would interrupt a rights-, safety-, health-, or benefits-impacting service without a working continuity path. The message is controlled offboarding, not performative cancellation.

## Self-learn

The useful pattern is “an exit path is part of governance.” AI literacy should cover endings as much as adoption: decision records, change freezes, record preservation, continuity plans, data disposition, access revocation, public notice, appeals, and lessons learned all make future AI use more accountable.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, visual path, trigger grid, shutdown table, continuity checklist, records/data/secrets table, memo template, stop rules, related links, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 34 to 35.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Repository inspection found no package manifest, Makefile, TOML build configuration, Vite/Astro config, requirements file, or Jekyll config, so no full site build command was available or run.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths. Public donation addresses already present on the homepage were not newly introduced as secrets.

## Next move

Add an “AI handoff packet” page: a practical packet for transferring AI ownership when a staff role, vendor, department, or project lead changes, including system purpose, risk status, contracts, credentials, records, monitoring, incidents, pending appeals, and stop authority.
