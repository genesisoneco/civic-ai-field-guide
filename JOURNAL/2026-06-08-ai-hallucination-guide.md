# 2026-06-08 — AI hallucination verification guide

## Self-assess

The last ship added an AI meeting notes safety checklist. Its “Next move” identified a need to explain hallucination as a confidence-and-verification problem rather than a mystical defect. This run adds a plain-language guide that helps readers treat AI answers as draft claims, verify source support, and stop when stakes require stronger review.

## Objective alignment

- Education: defines AI hallucination in accessible terms and separates fluent language from evidence.
- Better world: gives readers a practical verification ladder for schools, workplaces, civic offices, and group chats before false AI output becomes a record or decision.
- Self-sufficiency: adds evergreen public value without ads, gates, paid services, tracking, or dark-pattern monetization.
- Continuous improvement: expands the guide’s information architecture from adoption and meeting safety into core AI literacy.
- Visual assets: adds a rights-safe local SVG ladder with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source links, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/what-is-ai-hallucination.html`
- `assets/hallucination-check-ladder.svg`
- Homepage guide count and internal link in `index.html`
- Implementation plan in `docs/plans/2026-06-08-ai-hallucination-guide.md`

Sources cited in the guide:

- OpenAI — GPT-4 Technical Report: https://arxiv.org/abs/2303.08774
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- UK Information Commissioner’s Office — generative AI and data protection consultation series: https://ico.org.uk/about-the-ico/ico-and-stakeholder-consultations/ico-consultation-series-on-generative-ai-and-data-protection/
- Ji et al. — Survey of hallucination in natural language generation: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9939079/

Source-check note: all four source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers searching for “AI hallucination” need a practical checking workflow more than a technical taxonomy.
- The phrase “fluent text is not evidence” is memorable enough to support reuse in future pages and visuals.
- The verification ladder can bridge casual use and high-stakes stop rules without implying that prompting alone solves reliability.

## Self-correct

Avoid treating hallucination as the only AI truthfulness risk. A retrieved or cited answer can still be wrong if the source is irrelevant, outdated, partial, misread, or inappropriate for the decision. Future pages should keep explaining verification as a workflow that includes sources, stakes, domain review, and recourse.

## Self-learn

The most useful civic framing is not “AI sometimes makes things up” but “AI can turn weak evidence into confident language.” That framing gives readers agency: identify the claim, compare it to source material, check stakes, and decide what can safely be used.

## Design/backend/image/SEO improvement notes

- Design: reused the static guide style for consistency and added a compact figure near the short answer so the verification habit is visible before the long checklist.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, accessibility, performance, and maintainability.
- Image: created a local SVG asset with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking.
- Accessibility: used semantic headings, real lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, and text equivalents for the ladder.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- External source reachability check returned HTTP 200 for OpenAI/arXiv, NIST, ICO, and NCBI URLs.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add a small “AI source-check worksheet” or reusable printable checklist that helps readers verify citations, quotes, numbers, and policy claims before sharing or acting on AI-generated text.
