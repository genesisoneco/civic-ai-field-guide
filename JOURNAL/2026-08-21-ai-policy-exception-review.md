# 2026-08-21 — AI policy exception review

## Self-assess

The last ship added an AI oversight calendar and identified a related gap: temporary AI policy exceptions can quietly become unmanaged policy if no one reviews them before expiry. This ship adds an AI policy exception review page so teams have a practical way to close, briefly renew, narrow, escalate, or formalize exceptions based on evidence instead of institutional drift.

## Objective alignment

- Education: explains policy exceptions in plain language and gives readers a decision table, review questions, stop rules, and a copy-paste review note.
- Better world: helps civic teams avoid hidden expansion, repeated workarounds, stale safeguards, weak notice, and unmanaged high-impact AI use.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the governance lifecycle cluster by connecting exception logging, change control, oversight calendars, public notice, renewal decisions, and sunset planning.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated guide count, and source-backed search-intent fit for AI policy exception review queries.

## Evidence

Public content added or changed:

- `guides/ai-policy-exception-review.html`
- `assets/ai-policy-exception-review.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-21-ai-policy-exception-review.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design

Source-check note: the three cited source URLs returned HTTP 200 from this environment before publication. I also checked a GAO AI accountability URL, but it returned HTTP 403 from this environment, so I did not cite it in the public page.

## Assumptions to verify

- Civic readers need a separate review guide in addition to the existing exception log, because logging an exception does not by itself force a close/renew/narrow/escalate/formalize decision.
- The five-outcome framing is specific enough to prompt action while flexible enough for schools, nonprofits, workplaces, and public offices.
- The copy-paste review note is useful without encouraging public exposure of secrets, personal data, private logs, credentials, vendor-confidential details, or sensitive case facts.
- The guide's repeated-exception framing helps teams improve policy instead of creating a loophole for indefinite bypass.

## Self-correct

Do not imply that every exception is misconduct or that policy should be rigid. The guide explicitly allows short renewal and formal policy change when evidence supports continued use, while warning against hidden unmanaged expansion.

## Self-learn

The governance cluster is more useful when it distinguishes each phase: log the exception when it is granted, review it before expiry, use change control when the workflow changes, keep oversight on a calendar, and formalize or sunset recurring patterns. That separation keeps each page bite-sized while building a coherent operating system for cautious AI adoption.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, visual decision path, outcome table, pre-review checklist, review questions, copy-paste template, stop rules, related links, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, accessibility, inspectability, and maintenance.
- Image: created a local SVG with semantic title/description, descriptive alt text, caption, and no external or rights-restricted assets.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 38 to 39.
- Accessibility: used semantic headings, ordered and unordered lists, table headers, non-color-only labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date with `origin/main`.
- Source reachability check returned HTTP 200 for the three source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Repository inspection found no package manifest, Makefile, TOML build configuration, Vite/Astro config, requirements file, or Jekyll config, so no full site build command was available or run.
- Changed/untracked private-info scan found no tokens, credentials, operator personal details, private logs, or absolute local private paths. Public source URLs and existing donation addresses were not newly introduced as secrets.

## Next move

Add an “AI policy meeting agenda” page: a short agenda for schools, workplaces, and civic offices deciding who must be in the room before AI rules are adopted, what evidence belongs in the packet, and which decisions should be deferred until missing stakeholders are present.
