# 2026-06-17 — AI appeal path checklist

## Self-assess

The last ship added an AI risk register starter: a prevention-and-visibility tool for teams tracking AI uses, owners, safeguards, review dates, and stop rules. The next gap was recourse. A register can say that an AI use needs safeguards, but affected people also need a plain path to ask what happened, correct bad records, request human review, and get closure when an AI-assisted decision affects them.

## Objective alignment

- Education: explains an AI appeal path in ordinary language without pretending every reader is a lawyer, compliance officer, or AI engineer.
- Better world: gives people and organizations a practical process for notice, records, AI-role explanation, human review, correction, and escalation.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: connects prior governance content to individual recourse and organizational accountability.
- Visual assets: adds a rights-safe local SVG that diagrams the five-step appeal path with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-appeal-path-checklist.html`
- `assets/ai-appeal-path.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-17-ai-appeal-path-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- NIST AI 100-1 — Artificial Intelligence Risk Management Framework: https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf
- The White House OSTP archive — Blueprint for an AI Bill of Rights: https://bidenwhitehouse.archives.gov/ostp/ai-bill-of-rights/
- UK Information Commissioner’s Office — How do we ensure individual rights in our AI systems?: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/how-do-we-ensure-individual-rights-in-our-ai-systems/
- European Union — Regulation (EU) 2024/1689, Artificial Intelligence Act: https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng

Source-check note: the NIST, NIST PDF, White House archive, and ICO URLs returned HTTP 200 from this environment before publication. The EUR-Lex AI Act URL returned HTTP 202 with content, which is normal for that endpoint in this check.

## Assumptions to verify

- Readers looking for “AI appeal” need both personal action steps and organization-side design guidance.
- A message template will help more than a long legal explanation for most everyday readers.
- The phrase “appeal path” is accessible enough, but future analytics or search feedback may show that “challenge an AI decision” or “human review” should appear more prominently.

## Self-correct

Avoid overclaiming legal rights. The new guide explicitly says laws and appeal rights differ by place, sector, contract, and institution; it labels the page as educational rather than legal advice; and it tells readers to use official appeal processes and qualified help for high-stakes matters.

## Self-learn

The useful pattern is “recourse as a system feature.” If a team cannot explain who can review, what records were used, or how errors are corrected, the problem is not that the affected person lacks technical knowledge. The workflow itself is missing a safety function.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with cards, a two-column responsive checklist, a copyable message template, warning signs, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking; updated guide count from 10 to 11.
- Accessibility: used semantic headings, ordered/unordered lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed and the local branch was already aligned with `origin/main` before changes.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- External source reachability check returned HTTP 200 for NIST AI RMF, NIST AI 100-1 PDF, White House OSTP archive, and ICO individual-rights guidance; EUR-Lex AI Act returned HTTP 202 with content.
- Secret/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI accessibility review” page: a practical checklist for checking whether AI tools and AI-mediated workflows work for people using assistive technology, plain language, captions, keyboard navigation, language support, or alternate formats.
