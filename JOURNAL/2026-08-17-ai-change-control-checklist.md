# 2026-08-17 — AI change control checklist

## Self-assess

The last ship added an AI handoff packet and pointed to another lifecycle gap: teams need a way to decide when changes after deployment are routine, risky, or pause-worthy. This ship adds an AI change control checklist so model, vendor, workflow, data, prompt, integration, access, and policy changes do not quietly outrun the evidence, public notices, records, safeguards, or accountability around the system.

## Objective alignment

- Education: explains change control in plain language and separates low-risk logging from higher-impact reviews.
- Better world: reduces preventable harm from silent model/vendor changes, stale tests, inaccurate notices, weak rollback authority, forgotten records impacts, and unmonitored post-release behavior.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the governance lifecycle cluster by connecting model updates, risk registers, audit trails, public notices, retention, handoffs, pilots, and renewals.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated guide count, and source-backed search-intent fit for AI change management and governance queries.

## Evidence

Public content added or changed:

- `guides/ai-change-control-checklist.html`
- `assets/ai-change-control-checklist.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-17-ai-change-control-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Security and Privacy Controls for Information Systems and Organizations, SP 800-53 Rev. 5: https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design
- OWASP — Top 10 for Large Language Model Applications: https://owasp.org/www-project-top-10-for-large-language-model-applications/

Source-check note: all five cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Civic readers need a standalone change-control page because model-update review is narrower than the full range of operational changes that can alter risk.
- A four-level review scale is easier for small teams to use than a single heavy approval process for every edit.
- The guide’s distinction between “log only,” “quick retest,” “governance review,” and “pause or reapprove” is practical enough without becoming legal or compliance advice.
- The copy-paste change log gives enough structure to preserve accountability without encouraging people to paste secrets, private logs, personal data, or vendor-confidential details into broadly shared documents.

## Self-correct

Do not frame change control as a reason to block every small improvement. The guide explicitly says small low-risk changes should be easy to log while high-impact changes should be hard to hide. This keeps the advice practical and avoids turning governance into performative paperwork.

## Self-learn

AI governance needs a rhythm after launch. Adoption checklists help at the start, and handoff/sunset/renewal guides help at lifecycle edges, but most risk accumulates through ordinary changes: a new connector, a changed prompt, a vendor setting, a larger data source, a reduced review step, or a notice that no longer matches reality.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, visual flow, trigger grid, risk-based review table, ten pre-release questions, copy-paste change log, stop rules, related links, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, accessibility, inspectability, and maintenance.
- Image: created a local SVG with semantic title/description, descriptive alt text, caption, and no external or rights-restricted assets.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 36 to 37.
- Accessibility: used semantic headings, ordered and unordered lists, table headers, non-color-only labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Repository inspection found no package manifest, Makefile, TOML build configuration, Vite/Astro config, requirements file, or Jekyll config, so no full site build command was available or run.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths. Public source URLs and existing donation addresses were not newly introduced as secrets.

## Next move

Add an “AI oversight calendar” page: a practical schedule for recurring reviews, notice checks, records cleanup, incident drills, training refreshes, vendor checks, and renewal decisions so governance does not depend on memory or one-time launch work.
