# 2026-06-29 — AI detector limits and fair process

## Self-assess

The last ship added an AI evaluation evidence checklist. Its next-move note identified AI detector limits and fair process as the most useful follow-up because classrooms and organizations need a practical way to respond to suspected AI use without turning weak evidence into punishment. This ship adds a source-backed guide that treats detector output as an uncertain signal, then gives a calmer review path, evidence table, conversation script, and assignment/workflow design suggestions.

## Objective alignment

- Education: explains AI detector limits in plain language and distinguishes “signal worth reviewing” from “proof.”
- Better world: reduces harm from shortcut accusations, especially where false positives could affect students, workers, writers, multilingual people, or people using accessibility/language support.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the guide’s classroom and evidence-evaluation cluster with a practical due-process page.
- Visual assets: adds a rights-safe local SVG that diagrams the fair-process path, with SVG title/description, image alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-detector-limits-fair-process.html`
- `assets/ai-detector-fair-process.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-29-ai-detector-fair-process.md`

Sources cited in the guide:

- OpenAI — New AI classifier for indicating AI-written text: https://openai.com/index/new-ai-classifier-for-indicating-ai-written-text/
- OpenAI Help Center — How can educators respond to students presenting AI-generated content as their own?: https://help.openai.com/en/articles/8313351-how-can-educators-respond-to-students-presenting-ai-generated-content-as-their-own
- Cornell Center for Teaching Innovation — Generative AI, academic integrity, and AI detection: https://teaching.cornell.edu/generative-artificial-intelligence/ai-academic-integrity
- International Journal for Educational Integrity — Testing of detection tools for AI-generated text: https://edintegrity.biomedcentral.com/articles/10.1007/s40979-023-00146-z
- Liang et al. — GPT detectors are biased against non-native English writers: https://arxiv.org/abs/2304.02819
- UNESCO — Guidance for generative AI in education and research: https://www.unesco.org/en/articles/guidance-generative-ai-education-and-research

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a fair-process checklist more than a technical taxonomy of detector methods.
- The “detector result ≠ final decision” framing is strong enough to prevent misuse while still respecting legitimate integrity concerns.
- The conversation script will be useful to educators and managers who need wording that lowers conflict.
- Future work should add a guide on AI translation and language access because detector false-positive risks overlap with multilingual writing, accessibility support, and human review needs.

## Self-correct

Avoid overcorrecting into “detectors are always useless.” The guide says a detector can be one signal, but not the whole case. It recommends context, policy review, process evidence, conversation, documentation, and appeal rather than ignoring concerns or automating punishment.

## Self-learn

Fair-process guidance becomes more useful when it gives exact replacement behavior: neutral wording, review steps, evidence strength categories, and assignment design changes. This is more actionable than simply warning that detectors can be inaccurate.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, checklist sections, evidence table, conversation script, source list, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 15 to 16.
- Accessibility: used semantic headings, lists, a data table with headers, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` and `git pull --ff-only origin main` completed before changes and the branch was up to date.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for 16 structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI translation and language access” page: a practical guide to using AI translation carefully without erasing human review, cultural context, accessibility needs, privacy constraints, or appeal paths.
