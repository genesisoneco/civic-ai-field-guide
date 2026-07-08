# 2026-07-08 — AI system owner checklist

## Self-assess

The last ship added AI audit trail basics. Its next-move note identified ownership because audit records, consent, appeals, and incident response only work when someone has authority to answer questions, pause a workflow, and make corrections. This ship follows that thread with a practical, source-backed ownership checklist for schools, workplaces, public offices, nonprofits, newsrooms, and community teams.

## Objective alignment

- Education: explains AI workflow ownership in plain language, with concrete names, roles, pause triggers, and review questions.
- Better world: encourages accountability, human review, appeal access, incident handling, data stewardship, and safer pause/restart decisions.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the accountability cluster and updates homepage guide count and internal linking.
- Visual assets: adds a rights-safe local SVG showing the owner, reviewers, affected people, pause path, audit trail, and correction loop, with SVG title/description, image alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, homepage internal linking, and clear search-intent fit for teams asking “who owns this AI system?”

## Evidence

Public content added or changed:

- `guides/ai-system-owner-checklist.html`
- `assets/ai-system-owner-checklist.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-08-ai-system-owner-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- NIST — Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile (NIST AI 600-1): https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
- European Commission — AI Act overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai
- UK Information Commissioner’s Office — Guidance on AI and data protection: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/
- UK Information Commissioner’s Office — Accountability and governance guidance: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/accountability-and-governance/

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a lightweight ownership pattern more than a formal governance framework when they are starting from informal AI use.
- “Pause authority” should be as prominent as “accountability” because many real failures continue when nobody feels authorized to stop a workflow.
- Teams may confuse vendor responsibility with local accountability; the guide should keep making that distinction.
- Future work should add an AI public notice template because ownership and appeal paths become more useful when affected people can see clear, accessible notices.

## Self-correct

Avoid implying that one named owner can personally solve every legal, privacy, accessibility, labor, civil-rights, security, or procurement issue. The guide says ownership is a coordination role with authority and support, and it flags that high-stakes workflows need stronger review. It also avoids claiming specific legal compliance; it frames the material as public-interest guidance, not legal advice.

## Self-learn

The most useful ownership frame is not a hierarchy chart. It is a set of answerable questions: purpose, stakes, AI role, reviewer, pause trigger, records, and appeal path. Ownership becomes real when a person can explain the workflow, show evidence, pause use, and connect affected people to human review.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, role grid, decision table, starter owner record, pause-authority section, handoff triggers, bad-sign list, checklist, sources, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 19 to 20.
- Accessibility: used semantic headings, lists, a data table with headers, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 20 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI public notice template” page: starter language for telling communities when AI is used in a service or workflow, what it affects, who owns it, how to get human review, and how to request language or disability access.
