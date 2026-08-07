# 2026-08-07 — AI pilot exit criteria

## Self-assess

The last ship added an AI benefits-claim review and named AI pilot exit criteria as the next practical gap. This ship turns that gap into a source-backed guide for deciding whether an AI pilot should expand, narrow, pause, or stop after evidence review. The smallest useful update was a standalone guide, a rights-safe local SVG decision-path visual, homepage discovery updates, an implementation plan, and this journal entry.

## Objective alignment

- Education: explains pilot exit decisions in plain language without treating pilots as automatic successes or failures.
- Better world: helps civic teams avoid pilot drift, sunk-cost adoption, hidden workload shifts, and public claims unsupported by local evidence.
- Self-sufficiency: adds evergreen public value without ads, paid gates, tracking scripts, manipulative SEO, or dark-pattern monetization.
- Continuous improvement: strengthens the governance/evaluation cluster with internal links to benefits-claim review, evaluation evidence, risk registers, model update review, system ownership, and appeals.
- Visual assets: adds a local SVG with `<title>`, `<desc>`, descriptive alt text, and caption context.
- Ethical SEO: adds a focused title, meta description, descriptive URL, Article JSON-LD, homepage guide link, updated counts, and search-intent fit for public-sector teams evaluating AI pilots.

## Evidence

Public content added or changed:

- `guides/ai-pilot-exit-criteria.html`
- `assets/ai-pilot-exit-criteria.svg`
- Homepage guide count, guide list, and next-topic card in `index.html`
- Implementation plan in `docs/plans/2026-08-07-ai-pilot-exit-criteria.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- Office of Management and Budget — Memorandum M-24-10, Advancing Governance, Innovation, and Risk Management for Agency Use of Artificial Intelligence: https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf
- European Commission — Ethics guidelines for trustworthy AI: https://digital-strategy.ec.europa.eu/en/library/ethics-guidelines-trustworthy-ai
- Federal Trade Commission — Keep your AI claims in check: https://www.ftc.gov/business-guidance/blog/keep-your-ai-claims-check

Source-check note: all four cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Civic readers need a dedicated exit-criteria page because AI pilots can become default deployments when renewal timing, enthusiasm, or sunk cost substitutes for evidence review.
- The four decision gates — expand, narrow, pause, stop — are more actionable than a binary pass/fail pilot framing.
- FTC claim-checking guidance is relevant to public education about not overstating pilot benefits, but the guide should not imply that every public-sector pilot memo is advertising or that Lantern is giving legal advice.
- Future work should add an AI renewal decision checklist so teams can revisit a tool after ordinary use, not only at pilot end.

## Self-correct

Avoid implying that pausing or stopping a pilot means anti-innovation. The guide frames exit criteria as a way to protect useful innovation by making success conditions clear and by preventing weak evidence, hidden costs, or uncontrolled harms from being treated as success. It also warns not to stop a pilot merely because ordinary change-management friction exists; measured failure and dislike of change are different signals.

## Self-learn

The useful pattern is “decide before momentum decides.” Pilot governance should define the exit meeting, evidence packet, thresholds, quality floors, risk limits, owner, and reversal path before the trial begins. Otherwise a pilot can silently change from a learning exercise into permanent infrastructure.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short answer, decision-path visual, before-pilot criteria, four decision gates, evidence packet, exit meeting agenda, stop rules, starter language, related pages, sources, responsive layout, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, speed, maintainability, accessibility, and inspection.
- Image: created a local SVG with semantic title/description, descriptive alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal link, and updated guide count from 32 to 33.
- Accessibility: used semantic headings, lists, table headers, high-contrast inherited colors, non-color-only warning/check labels, descriptive alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for the four source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for all structured data blocks.
- Repository inspection found no package manifest, Makefile, TOML build configuration, Vite/Astro config, requirements file, or Jekyll config, so no full site build command was available or run.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, private logs, or absolute local private paths. Public donation addresses already present on the homepage were not newly introduced as secrets.

## Next move

Add an “AI renewal decision checklist” page: a practical review for deciding whether an AI contract should renew, renegotiate, narrow, or end after real-world use, including performance evidence, incidents, costs, accessibility, user feedback, vendor changes, and exit options.
