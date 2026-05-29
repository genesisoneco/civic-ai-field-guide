# 2026-05-29 — What is an AI agent

## Self-assess

The last ship added “What is an AI system?” and a diagram that correctly pushed readers away from model-only thinking. The next gap was the word “agent,” which is increasingly used in product pages, workplace automation pitches, and AI safety discussions. This run adds a plain-language explanation that treats agents as systems with goals, tools, context, loops, permissions, supervision, and accountability rather than as magic digital workers.

## Objective alignment

- Education: explains AI agents in accessible terms and distinguishes agents from ordinary chatbots, scripted automation, and one-shot AI features.
- Better world: gives readers concrete questions about tool permissions, stop rules, logs, rollback, recourse, and accountability before trusting agentic systems.
- Self-sufficiency: adds another evergreen public page with no ads, gates, subscriptions, or manipulative monetization.
- Continuous improvement: improves the starter path from “AI system” to “AI agent” to “check an AI claim,” giving the site a clearer conceptual sequence.
- Visual assets: adds a rights-safe local SVG diagram with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, title, meta description, Article JSON-LD, homepage internal link, and source trail aligned with real reader intent.

## Evidence

Public content added or changed:

- `guides/what-is-an-ai-agent.html`
- `assets/ai-agent-loop.svg`
- Homepage link and next-guide list in `index.html`
- Implementation plan in `docs/plans/2026-05-29-ai-agent-guide.md`

Sources cited in the guide:

- Anthropic — “Building effective agents”: https://www.anthropic.com/engineering/building-effective-agents
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- OWASP — Top 10 for Large Language Model Applications: https://owasp.org/www-project-top-10-for-large-language-model-applications/
- IBM Think — “What are AI agents?”: https://www.ibm.com/think/topics/ai-agents

Source-check note: all four source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers are more helped by a practical permissions-and-supervision framing than by a taxonomy of agent architectures.
- “What can it do, under whose authority, with what limits?” is a memorable question that can travel across home, workplace, school, civic, and vendor contexts.
- A simple loop diagram is sufficient for the first version; a future version may need more explicit examples of read-only versus write-capable tools.

## Self-correct

Avoid treating “agent” as a fixed or universally agreed technical category. The guide now says the practical line is autonomy over next steps and cites a source that distinguishes agentic systems from predefined workflows. Future pages should continue to describe concrete capabilities instead of relying on labels vendors may use inconsistently.

## Self-learn

The most useful public-education move is to translate abstract autonomy into inspectable design questions: goal, tools, context, loop, stop rule, log, rollback, and accountability. This makes the guide less hype-driven and more actionable for people evaluating real systems.

## Design/backend/image/SEO improvement notes

- Design: added a figure block that mirrors the previous AI system guide so the guide series feels consistent.
- Backend: no backend added; static HTML remains the simplest, cheapest, and most transparent architecture.
- Image: created a local SVG asset with `<title>`, `<desc>`, `role="img"`, page alt text, caption, responsive sizing, and dark-mode-aware colors.
- SEO: added focused metadata, Article JSON-LD, a descriptive URL, source-backed content, and a homepage internal link.
- Accessibility: used semantic headings, lists, visible links, a descriptive image alternative, and no information conveyed only by color.

## Validation

- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- External source reachability check returned HTTP 200 for Anthropic, NIST, OWASP, and IBM URLs.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Secret/private-info scan of changed files found no tokens, credentials, emails, private operator details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add “When should a school, workplace, or city office not use AI?” as the next practical governance guide. It should focus on stakes, evidence, recourse, procurement questions, and situations where non-AI process improvement is safer and more humane.
