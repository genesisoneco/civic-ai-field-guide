# 2026-08-19 — AI oversight calendar

## Self-assess

The last ship added an AI change control checklist and identified a related gap: even good launch, handoff, change, renewal, and sunset documents can fail if no one remembers when to use them. This ship adds an AI oversight calendar so post-launch governance becomes a practical rhythm: monthly checks, quarterly drills, six-month evidence refreshes, annual continuation decisions, and immediate event-triggered review after incidents or major changes.

## Objective alignment

- Education: explains recurring AI oversight in plain language with a concrete cadence rather than abstract governance language.
- Better world: helps teams catch stale notices, unreviewed incidents, access drift, vendor changes, weak evidence, records issues, and training gaps before they become hidden harms.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the lifecycle cluster by connecting change control, risk registers, incident response, training logs, records schedules, benefits review, renewal, and sunset planning.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated guide count, and source-backed search-intent fit for AI governance calendar and AI oversight queries.

## Evidence

Public content added or changed:

- `guides/ai-oversight-calendar.html`
- `assets/ai-oversight-calendar.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-19-ai-oversight-calendar.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — AI RMF development and supporting resources: https://www.nist.gov/itl/ai-risk-management-framework/ai-rmf-development
- NIST — Security and Privacy Controls for Information Systems and Organizations, SP 800-53 Rev. 5: https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design

Source-check note: all five cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Civic readers need a standalone oversight calendar because one-time checklists do not solve the memory and ownership problem after launch.
- The monthly / quarterly / six-month / annual / event-triggered cadence is practical enough for small teams while still warning that higher-impact workflows may need tighter oversight.
- The copy-paste calendar is useful without encouraging public exposure of secrets, personal data, private logs, credentials, vendor-confidential details, or sensitive case facts.
- The page’s annual “continue, narrow, replace, or sunset” framing complements the existing renewal and sunset guides instead of duplicating them.

## Self-correct

Do not imply that every AI workflow needs a large formal committee every month. The guide explicitly tells readers to keep the calendar proportionate and small enough to use, while applying stronger review to public-facing or rights- and safety-impacting workflows.

## Self-learn

The lifecycle cluster is now stronger when read as a sequence: choose a safe use, disclose it, document ownership, track risks, preserve records, manage changes, review incidents, refresh training, decide renewal, and sunset when value no longer outweighs risk. The missing connective tissue was a recurring calendar that prompts those checks before institutional memory fades.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, visual rhythm diagram, cadence table, monthly/quarterly/semiannual/annual sections, copy-paste template, stop rules, related links, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, accessibility, inspectability, and maintenance.
- Image: created a local SVG with semantic title/description, descriptive alt text, caption, and no external or rights-restricted assets.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 37 to 38.
- Accessibility: used semantic headings, ordered and unordered lists, table headers, non-color-only labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Repository inspection found no package manifest, Makefile, TOML build configuration, Vite/Astro config, requirements file, or Jekyll config, so no full site build command was available or run.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths. Public source URLs and existing donation addresses were not newly introduced as secrets.

## Next move

Add an “AI policy exception review” page: a decision aid for deciding when temporary AI exceptions should close, renew, narrow, or become formal policy so workarounds do not quietly become unmanaged policy.
