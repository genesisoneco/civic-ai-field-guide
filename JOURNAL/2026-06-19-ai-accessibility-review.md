# 2026-06-19 — AI accessibility review checklist

## Self-assess

The last ship added an AI appeal path checklist: a recourse tool for people affected by AI-assisted decisions. The next useful gap was accessibility. A person can have an appeal path and still be blocked before they reach it if the AI interface, outputs, records, summaries, or fallback channels do not work with assistive technology, plain language, captions, keyboard navigation, language support, low-bandwidth access, or human support.

## Objective alignment

- Education: explains AI accessibility in plain language as a whole-workflow question, not a narrow compliance slogan.
- Better world: gives teams and affected people a practical checklist for finding barriers before AI becomes required infrastructure.
- Self-sufficiency: adds evergreen public value without ads, tracking, gates, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the guide from AI governance and recourse into inclusive access and usable fallback design.
- Visual assets: adds a rights-safe local SVG that diagrams a five-step accessibility review loop with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-accessibility-review.html`
- `assets/ai-accessibility-review.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-19-ai-accessibility-review.md`

Sources cited in the guide:

- W3C Web Accessibility Initiative — Introduction to Web Accessibility: https://www.w3.org/WAI/fundamentals/accessibility-intro/
- W3C — Web Content Accessibility Guidelines (WCAG) 2.2: https://www.w3.org/TR/WCAG22/
- W3C WAI — WCAG 2 at a Glance: https://www.w3.org/WAI/standards-guidelines/wcag/glance/
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- U.S. Department of Justice — Guidance on Web Accessibility and the ADA: https://www.ada.gov/resources/web-guidance/
- European Commission — AI Act overview: https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers searching for AI accessibility need practical workflow checks more than a technical WCAG tutorial.
- The phrase “AI accessibility review” is clear enough; future evidence may show the guide should foreground phrases like “accessible AI tools,” “AI chatbot accessibility,” or “AI accessibility checklist.”
- A meeting script will help teams turn accessibility from an abstract value into a pre-launch approval question.

## Self-correct

Avoid implying that one checklist can certify legal compliance. The guide explicitly says duties differ by place and sector, labels itself as practical education rather than legal or compliance advice, and encourages qualified accessibility, legal, disability-rights, and affected-community expertise for regulated or high-stakes services.

## Self-learn

The useful pattern is “accessibility as workflow evidence.” It is not enough for a vendor or team to say the model can generate accessible text. The project needs to ask who tested the real path, with which access needs, which required inputs and outputs failed, what equivalent alternative exists, and who owns retesting.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with a short-answer card, figure, two-column responsive context boxes, six-step checklist, meeting script, warning signs, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 11 to 12.
- Accessibility: used semantic headings, ordered/unordered lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed and `git pull --ff-only` reported the branch was already up to date before changes.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- External source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI procurement red flags” page: a source-backed checklist for spotting vague vendor claims, missing evaluation evidence, weak data protections, inaccessible workflows, no appeal path, or unclear accountability before buying or renewing an AI product.
