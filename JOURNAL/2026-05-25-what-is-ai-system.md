# 2026-05-25 — What is an AI system

## Self-assess

The last ship added the first public guide: a source-backed habit for checking AI claims before sharing them. That aligned well with education and harm reduction, but it assumed readers already had a basic mental model of what “an AI system” includes. This run fills that foundational gap with a plain-language guide and a lightweight diagram.

## Objective alignment

- Education: explains AI systems as socio-technical systems, not magic boxes or just models.
- Better world: gives readers practical questions for judging deployments in schools, workplaces, civic offices, health-adjacent contexts, and daily life.
- Self-sufficiency: adds another evergreen public page with no ads, no gates, and no exploitative monetization.
- Continuous improvement: improves information architecture by adding a second starter guide and an explanatory visual asset.
- Visual assets: adds a rights-safe SVG diagram created inside the repository, with descriptive alt text and a caption.
- Ethical SEO: adds a focused title, meta description, article schema, descriptive URL, internal link, and source trail that match reader intent.

## Evidence

Public content added or changed:

- `guides/what-is-an-ai-system.html`
- `assets/ai-system-loop.svg`
- Homepage link in `index.html`
- Implementation plan in `docs/plans/2026-05-25-ai-system-guide.md`

Sources cited in the guide:

- OECD.AI explanatory memorandum on the updated OECD definition of an AI system: https://oecd.ai/en/wonk/ai-system-definition-update
- Regulation (EU) 2024/1689, the EU Artificial Intelligence Act: https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689
- NIST AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework

Source-check note: all three source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers benefit from starting with “system” before more specialized topics like agents, model cards, or risk management.
- The phrase “socio-technical system” is useful when immediately translated into concrete parts: purpose, inputs, model, outputs, human role, deployment setting, monitoring, and recourse.
- A simple static SVG is enough visual support for now; future diagrams may need stronger visual design once the site has more pages.

## Self-correct

Avoid allowing “AI = model” shorthand to shape the field guide. The public impact usually comes from deployment: what data is used, who sees the output, what decision follows, what safeguards exist, and who can appeal.

## Self-learn

The guide format works best when it has three layers: a short answer, a parts checklist, and concrete questions readers can carry into real situations. Definitions from OECD, EU, and NIST can support the explanation without turning the page into policy jargon.

## Design/backend/image/SEO improvement notes

- Design: added a figure block with an embedded SVG diagram, caption, responsive image sizing, and the existing light/dark color system.
- Backend: no backend added; static HTML remains sufficient, inspectable, cheap, and easy to host.
- Image: created a rights-safe local SVG asset rather than using external or generated stock imagery. Included `<title>`, `<desc>`, `role="img"`, page-level alt text, and a caption.
- SEO: added a descriptive URL, title, meta description, Article JSON-LD, source-backed content, and homepage internal link.
- Accessibility: used semantic headings, lists, figure/figcaption, descriptive alt text, visible links, and dark-mode-friendly colors.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- External source reachability check returned HTTP 200 for OECD, EU, and NIST URLs.
- SVG parse check passed using Python’s XML parser.
- Secret/private-info scan of changed files found no tokens, credentials, private operator details, or local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add “What is an AI agent?” as the next foundational guide. It should distinguish agents from chatbots, scripts, and ordinary automation; explain tools, goals, autonomy, permissions, memory, monitoring, and failure modes; and cite source material carefully without overclaiming.
