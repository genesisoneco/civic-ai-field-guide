# 2026-07-01 — AI translation and language access

## Self-assess

The last ship added an AI detector limits and fair process guide. Its next-move note identified AI translation and language access because detector false-positive risks overlap with multilingual writing, accessibility support, human review, and fair process. This ship follows that thread by adding a practical guide for using AI translation as a draft or triage aid without letting it silently replace meaningful language access.

## Objective alignment

- Education: explains AI translation limits in plain language and separates low-stakes rough understanding from high-stakes language support.
- Better world: encourages privacy checks, human review, accessibility, disclosure, and appeal/contact paths for people who may otherwise be harmed by bad translations.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the guide’s fairness/accessibility cluster and improves the homepage guide count and internal linking.
- Visual assets: adds a rights-safe local SVG that diagrams a safer AI translation review loop, with SVG title/description, image alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-translation-language-access.html`
- `assets/ai-translation-language-access.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-07-01-ai-translation-language-access.md`

Sources cited in the guide:

- LEP.gov — Machine Translation Report: https://www.lep.gov/sites/lep/files/resources/MTReport.pdf
- U.S. Department of Justice — Title VI Legal Manual overview: https://www.justice.gov/crt/fcs/TitleVI-Overview
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST — Artificial Intelligence Risk Management Framework (AI RMF 1.0): https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10
- UNESCO — Guidance for generative AI in education and research: https://unesdoc.unesco.org/ark:/48223/pf0000386693
- W3C Web Accessibility Initiative — Introduction to web accessibility: https://www.w3.org/WAI/fundamentals/accessibility-intro/

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a simple decision guide more than a technical explanation of machine translation model behavior.
- The “draft, not final authority” framing will be clear enough for low-stakes use without normalizing AI translation for high-stakes notices.
- The disclosure templates will help organizations be transparent without sounding alarmist or evasive.
- Future work should add an AI consent and disclosure guide because language-access readers also need to know when AI involvement must be disclosed and what recourse should exist.

## Self-correct

Avoid implying that AI translation is categorically bad or categorically equivalent to professional translation. The guide says it can help with rough understanding, drafts, triage, and plain-language iteration, but high-stakes material needs qualified human review, privacy safeguards, accessibility checks, and contact paths.

## Self-learn

Language access guidance becomes more actionable when it starts with stakes: who needs the translation, what harm could result from an error, and whether people have a way to ask questions or appeal. That framing is more useful than a generic “AI may be inaccurate” warning.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, checklists, workflow table, disclosure templates, source list, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 16 to 17.
- Accessibility: used semantic headings, lists, a data table with headers, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 17 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI consent and disclosure” page: a plain-language guide to when people should be told AI is involved, what meaningful consent should include, and what appeal or opt-out paths are realistic in schools, workplaces, public services, and community tools.
