# 2026-07-03 — AI consent and disclosure

## Self-assess

The last ship added an AI translation and language access guide. Its next-move note identified AI consent and disclosure because people cannot safely question, refuse, or appeal AI-mediated systems when the AI role is hidden or described only in vague policy language. This ship follows that thread with a practical guide that separates simple disclosure from meaningful consent, human review, and refusal paths.

## Objective alignment

- Education: explains AI disclosure, consent, review, refusal, and appeal in plain language for schools, workplaces, public offices, and community groups.
- Better world: encourages clear notice, privacy awareness, accessibility, non-AI alternatives, and human review before AI affects high-stakes decisions.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the guide’s governance and accountability cluster and updates homepage guide count and internal linking.
- Visual assets: adds a rights-safe local SVG that diagrams a notice-to-consent ladder, with SVG title/description, image alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-consent-disclosure.html`
- `assets/ai-consent-disclosure.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-03-ai-consent-disclosure.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- Archived White House OSTP — Blueprint for an AI Bill of Rights: https://bidenwhitehouse.archives.gov/ostp/ai-bill-of-rights/
- UNESCO — Guidance for generative AI in education and research: https://unesdoc.unesco.org/ark:/48223/pf0000386693
- European Commission — AI Act overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai

Source-check note: all five source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a practical decision table more than a detailed legal taxonomy of consent, notice, automated decision-making, and data protection.
- The guide’s “more impact means more explanation, choice, and review” ladder is easier to apply than a binary rule that says every AI use needs identical consent.
- The disclosure templates are useful as starter language, but future work may need sector-specific versions for schools, workplaces, public services, and health-related settings.
- Future work should add an AI audit trail basics guide because consent, disclosure, and appeal paths all depend on records that show what happened and who reviewed it.

## Self-correct

Avoid implying that disclosure alone makes an AI system ethical, legal, accurate, or safe. The guide explicitly says vague labels do not fix unsafe design, biased data, inaccessible workflows, privacy problems, or missing appeal paths. It also labels the content as public education rather than legal advice.

## Self-learn

Consent guidance is clearest when it starts from power and stakes. Low-risk AI assistance may need visible notice and a correction path; high-stakes, sensitive, or unavoidable AI use needs human review, refusal or alternative paths where feasible, and records of complaints and corrections.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, comparison boxes, decision table, templates, checklist, bad-sign list, sources, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 17 to 18.
- Accessibility: used semantic headings, lists, a data table with headers, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all five source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 18 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI audit trail basics” page: a plain-language guide to what teams should record about AI tools, prompts or inputs where appropriate, versions, decisions, human review, incidents, corrections, and consent or appeal events so future audits can reconstruct what happened without collecting more personal data than necessary.
