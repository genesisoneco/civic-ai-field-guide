# 2026-06-10 — AI source-check worksheet

## Self-assess

The last ship added a plain-language guide to AI hallucination and identified a practical next move: a reusable worksheet for checking citations, quotes, numbers, and policy claims. This run turns that next move into a printable guide page so readers can move from “AI can be wrong” to “here is the exact source trail I checked before relying on this sentence.”

## Objective alignment

- Education: gives readers a concrete method for source-checking AI output instead of treating verification as an abstract warning.
- Better world: reduces the chance that unsupported AI-generated citations, quotes, numbers, or policy claims become public records, classroom materials, workplace decisions, or group-chat misinformation.
- Self-sufficiency: adds evergreen public value without ads, gates, paid services, trackers, or manipulative monetization.
- Continuous improvement: expands the guide from explanatory pages into a reusable worksheet format that can support future printable tools.
- Visual assets: adds a rights-safe local SVG flow with title, description, alt text, and explanatory caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source links, print-friendly structure, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-source-check-worksheet.html`
- `assets/source-check-worksheet.svg`
- Homepage guide count and internal link in `index.html`
- Implementation plan in `docs/plans/2026-06-10-ai-source-check-worksheet.md`

Sources cited in the worksheet:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- World Health Organization — Ethics and governance of artificial intelligence for health: https://www.who.int/publications/i/item/9789240029200
- Mike Caulfield — SIFT: The Four Moves: https://hapgood.us/2019/06/19/sift-the-four-moves/

Source-check note: the three cited source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers who understand hallucination still need a tactile worksheet to apply verification under time pressure.
- A four-box format is short enough for classrooms, civic offices, and teams while still covering the major source-trail failure modes.
- Print CSS is useful for teachers, meeting facilitators, and public-interest readers even though the site is primarily web-first.

## Self-correct

Do not imply that source-checking makes every AI-assisted decision safe. A source can be real and accurately quoted while still being incomplete, biased, outdated, or inappropriate for the decision. The worksheet now asks for scope, date, missing limits, stakes, and safe next action rather than treating “found a source” as the finish line.

## Self-learn

The useful civic pattern is “one worksheet per important claim.” Trying to verify an entire AI answer at once hides risk. Breaking the answer into exact claims makes uncertainty visible and gives readers an action menu: use, revise, cite the source instead, ask an expert, run a test, or stop.

## Design/backend/image/SEO improvement notes

- Design: added a printable two-by-two worksheet grid and a simple four-step SVG flow so the page works both as a web guide and a handout.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking.
- Accessibility: used semantic headings, ordered/unordered lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, and print styles that preserve the worksheet text.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- External source reachability check returned HTTP 200 for the NIST, WHO, and Mike Caulfield URLs cited by the new worksheet.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI incident response” guide for teams that discover an AI-assisted mistake has already reached a user, record, publication, or decision.
