# 2026-08-14 — AI handoff packet

## Self-assess

The last ship added an AI sunset plan starter and identified a related lifecycle gap: what happens when ownership changes before a system ends. This ship adds a practical AI handoff packet so teams can transfer responsibility without losing purpose, scope limits, open risks, records context, credential control, monitoring duties, vendor obligations, or stop authority.

## Objective alignment

- Education: explains AI handoffs in plain language as a continuity and governance practice, not a bureaucratic formality.
- Better world: reduces avoidable harm from stale notices, unknown owners, dormant credentials, unread dashboards, unresolved incidents, and missing appeal paths.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the lifecycle governance cluster by linking system ownership, audit trails, risk registers, model updates, renewals, sunsets, and records retention.
- Visual assets: adds a rights-safe local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated guide count, and practical search-intent fit for teams transferring AI responsibility.

## Evidence

Public content added or changed:

- `guides/ai-handoff-packet.html`
- `assets/ai-handoff-packet.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-14-ai-handoff-packet.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design
- U.S. National Archives and Records Administration — Records scheduling: https://www.archives.gov/records-mgmt/scheduling
- Federal Trade Commission — Data Breach Response: A Guide for Business: https://www.ftc.gov/business-guidance/resources/data-breach-response-guide-business

Source-check note: the five cited source URLs returned HTTP 200 from this environment before publication. A GAO AI accountability source was considered but not used because the environment received HTTP 403 for that URL during source reachability checks.

## Assumptions to verify

- Civic readers need a standalone handoff page because ownership transfer is common and is not fully covered by owner, audit-trail, renewal, or sunset pages.
- The packet sections — purpose, roles, risk status, evidence, records/data, credentials/vendors, communication, and stop authority — are enough for a small team without becoming an enterprise governance manual.
- The 45-minute transfer meeting format is short enough to be used in real offices and complete enough to reveal missing context.
- The guide correctly avoids telling readers to store secrets in documents by separating shareable handoff context from restricted credential inventories.

## Self-correct

Do not imply that every handoff document should contain sensitive operational details. The guide explicitly says not to paste API keys, passwords, tokens, private logs, personal data, or vendor secrets into the packet, and recommends a redacted shareable version plus a restricted operational inventory.

## Self-learn

Lifecycle governance is not only adoption, renewal, and shutdown. Ownership transitions are risk events too. A public education guide should help teams preserve institutional memory before staff turnover, vendor changes, department moves, or project transitions turn manageable AI risks into invisible ones.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, visual map, trigger grid, packet contents table, 45-minute meeting agenda, copy-paste packet, stop rules, related links, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 35 to 36.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

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

Add an “AI change control checklist” page: a lightweight review for deciding when model, vendor, workflow, data, prompt, integration, or policy changes require retesting, notice updates, records review, and renewed stop rules.
