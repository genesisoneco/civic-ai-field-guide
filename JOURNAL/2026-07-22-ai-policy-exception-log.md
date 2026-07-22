# 2026-07-22 — AI policy exception log

## Self-assess

The last ship added an AI model update review checklist and named an AI policy exception log as the next practical gap. This ship fills that gap with a template for documenting temporary deviations from AI policy before they become invisible precedent. The smallest useful update was a source-backed guide, a local SVG lifecycle diagram, homepage discovery updates, and this journal entry.

## Objective alignment

- Education: explains policy exceptions in plain language as time-boxed governance records, not as bureaucracy or permission to ignore rules.
- Better world: helps schools, nonprofits, civic offices, and teams preserve accountability when urgent accessibility, service-continuity, vendor, or workflow issues require temporary workarounds.
- Self-sufficiency: adds evergreen public value without ads, paid gates, dark patterns, tracking scripts, or exploitative monetization.
- Continuous improvement: expands the governance cluster with internal links to audit trails, risk registers, system owners, incident response, public notice, data minimization, retention, deletion, accessibility, and model update review pages.
- Visual assets: adds a rights-safe local SVG lifecycle diagram with `<title>`, `<desc>`, alt text, and caption.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for teams looking for AI policy exception documentation.

## Evidence

Public content added or changed:

- `guides/ai-policy-exception-log.html`
- `assets/ai-policy-exception-log.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-07-22-ai-policy-exception-log.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- U.S. Office of Management and Budget — M-24-10: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design
- UK Information Commissioner’s Office — Artificial intelligence guidance: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/

Source-check note: the five cited source URLs returned HTTP 200 from this environment before publication. A GAO AI accountability page was considered but not cited because this environment received HTTP 403 during source reachability checking.

## Assumptions to verify

- Readers need a simple exception log because many AI governance failures come from small “temporary” workarounds that are never revisited.
- A lifecycle diagram improves understanding by emphasizing expiry and closure, not just approval.
- Future work should add an AI document intake checklist because uploads, attachments, records, and screenshots are a common path for accidental privacy or confidentiality exposure.

## Self-correct

Avoid making exception logs sound like a loophole or a substitute for legal, privacy, accessibility, procurement, labor, records, or security review. The guide states that the policy still matters, exceptions are temporary, and higher-impact exceptions need stronger approval. It also avoids overclaiming that logging itself makes an AI use safe; logging only makes the decision visible and reviewable.

## Self-learn

The useful pattern is “exception plus expiry.” An exception without a review date is policy erosion. A repeated exception is evidence about the policy, vendor, training, workflow, or procurement environment — not merely an administrative renewal.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, lifecycle figure, trigger checklist, log-fields table, safeguard grid, expiry rules, warning signs, starter language, print styles, and source list.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 25 to 26.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only checklist marks, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 26 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI document intake checklist” page: a practical checklist for deciding which documents are safe, appropriate, and useful to upload into AI tools — and which should stay out.
