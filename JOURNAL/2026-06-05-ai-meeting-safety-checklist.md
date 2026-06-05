# 2026-06-05 — AI meeting notes safety checklist

## Self-assess

The last ship added an AI vendor disclosure checklist. Its next practical gap was day-to-day use: many teams adopt AI meeting bots before they have procurement paperwork, retention rules, consent practices, or review habits. This run adds a meeting-notes checklist that turns privacy, security, accessibility, and records concerns into a pre-meeting/during-meeting/after-meeting workflow.

## Objective alignment

- Education: explains AI meeting transcription and summary risks in plain language without treating the tools as magical or inherently unsafe.
- Better world: gives teams, schools, nonprofits, and public offices concrete safeguards before sensitive conversations are captured or misrepresented.
- Self-sufficiency: adds evergreen public value without ads, gates, paid services, tracking, or dark-pattern monetization.
- Continuous improvement: expands the guide from adoption due diligence into everyday operational practice.
- Visual assets: adds a rights-safe local SVG safety loop with title, description, alt text, and a contextual caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, public source links, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-meeting-notes-safety-checklist.html`
- `assets/meeting-notes-safety.svg`
- Homepage guide count and internal link in `index.html`
- Implementation plan in `docs/plans/2026-06-05-ai-meeting-safety-checklist.md`

Sources cited in the guide:

- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- UK Information Commissioner’s Office — generative AI and data protection consultation series: https://ico.org.uk/about-the-ico/ico-and-stakeholder-consultations/ico-consultation-series-on-generative-ai-and-data-protection/
- OWASP — Top 10 for Large Language Model Applications: https://owasp.org/www-project-top-10-for-large-language-model-applications/
- CISA — Secure by Design: https://www.cisa.gov/resources-tools/resources/secure-by-design
- U.S. National Archives and Records Administration — Records Management: https://www.archives.gov/records-mgmt

Source-check note: all five source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers need a short operational checklist more than a long policy essay about meeting bots.
- The warning about draft summaries becoming false records is useful across workplaces, schools, nonprofits, and public-sector settings without becoming jurisdiction-specific legal advice.
- A reusable meeting notice template helps teams act immediately and encourages correction windows.

## Self-correct

Avoid implying that consent alone solves the risk. The page also requires data boundaries, retention awareness, human review, accurate labeling, correction windows, and deletion of unneeded material. Future pages should keep separating “AI made this easier” from “AI made this ready to trust.”

## Self-learn

The vendor checklist asks whether an AI system is accountable before purchase. The meeting checklist asks whether a specific use is accountable before capture. Civic AI literacy needs both levels: buying safeguards and everyday-use habits.

## Design/backend/image/SEO improvement notes

- Design: reused the static guide style for consistency and organized the page by before/during/after meeting flow.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, accessibility, and maintainability.
- Image: created a local SVG asset with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, and homepage internal linking.
- Accessibility: used semantic headings, real lists, visible links, strong contrast inherited from the guide template, non-color-only meaning, alt text, and a text notice template instead of image-only instructions.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- External source reachability check returned HTTP 200 for NIST, ICO, OWASP, CISA, and NARA URLs.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add a short glossary entry or guide explaining “AI hallucination” as a confidence-and-verification problem rather than a mystical model defect, with examples and practical checks.
