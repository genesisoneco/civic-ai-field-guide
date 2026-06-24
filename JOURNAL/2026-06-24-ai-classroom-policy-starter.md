# 2026-06-24 — AI classroom policy starter

## Self-assess

The last ship added an AI procurement red flags guide. That improved pre-purchase decision quality, but the guide still needed a practical bridge for schools and classrooms where AI is already appearing in homework, tutoring, writing, accessibility support, and assessment. This ship adds a starter classroom policy that names when AI use is allowed, limited, cited, or off-limits.

## Objective alignment

- Education: explains classroom AI expectations in plain language without hype, doom, or punishment-first framing.
- Better world: gives teachers, students, school leaders, families, and tutors a concrete way to discuss learning goals, privacy, accessibility, equity, and disclosure before conflict happens.
- Self-sufficiency: adds evergreen public value without ads, gates, tracking, paid services, dark patterns, or exploitative monetization.
- Continuous improvement: expands the field guide’s information architecture into education policy and classroom practice.
- Visual assets: adds a rights-safe local SVG that diagrams policy lanes with title, description, alt text, and caption.
- Ethical SEO: adds a descriptive URL, focused title and meta description, Article JSON-LD, source-backed headings, and homepage internal linking.

## Evidence

Public content added or changed:

- `guides/ai-classroom-policy-starter.html`
- `assets/ai-classroom-policy-starter.svg`
- Homepage guide count, guide list, and next-topic cards in `index.html`
- Implementation plan in `docs/plans/2026-06-24-ai-classroom-policy-starter.md`

Sources cited in the guide:

- UNESCO — Guidance for generative AI in education and research: https://www.unesco.org/en/articles/guidance-generative-ai-education-and-research
- U.S. Department of Education — Artificial Intelligence and Future of Teaching and Learning: https://www.ed.gov/sites/ed/files/documents/ai-report/ai-report.pdf
- TeachAI — AI Guidance for Schools Toolkit: https://teachai.org/toolkit
- NIST — AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- OECD.AI — OECD AI Principles overview: https://oecd.ai/en/ai-principles
- W3C WAI — Introduction to web accessibility: https://www.w3.org/WAI/fundamentals/accessibility-intro/

Source-check note: all six source URLs returned HTTP 200 from this environment before publication.

## Assumptions to verify

- Readers searching for classroom AI help need a short starter policy more than a long institutional policy template.
- The four-lane structure — allowed, limited, cited, off-limits — is understandable enough for students and teachers without legal vocabulary.
- A disclosure template will reduce ambiguity better than a generic “cite AI” instruction.
- The guide’s caution about AI detectors is useful, but future work may need a dedicated source-backed page on detector limits and fair academic integrity processes.

## Self-correct

Avoid implying that one classroom AI policy can solve academic integrity, privacy, accessibility, or equity concerns. The guide labels itself a starting point, not legal or school-board advice, and recommends approved tools, human review, accessible alternatives, and privacy safeguards.

## Self-learn

Education guidance works best when it starts with the learning goal, not the tool. A policy that distinguishes brainstorming, practice, disclosure, assessment, privacy, accessibility, and human support is more useful than a blanket “AI allowed” or “AI banned” rule.

## Design/backend/image/SEO improvement notes

- Design: added a scannable guide with short-answer card, figure, policy lanes, disclosure template, teacher checklist, detector caution, source list, and print styles.
- Backend: no backend added; static HTML remains appropriate for low-cost hosting, auditability, speed, accessibility, and maintainability.
- Image: created a local SVG with `<title>`, `<desc>`, semantic alt text, and caption; no external or rights-restricted image was used.
- SEO: added focused page title, meta description, Article JSON-LD, descriptive slug, source-backed headings, homepage internal linking, and updated guide count from 13 to 14.
- Accessibility: used semantic headings, ordered/unordered lists, high-contrast inherited colors, non-color-only meaning, alt text, SVG title/description, responsive layout, and print styles.

## Validation

- `git fetch origin main` completed before changes and `git status --short --branch` showed `main` aligned with `origin/main`.
- Source reachability check returned HTTP 200 for all six source URLs cited in the new guide.
- `git diff --check` passed.
- HTML parse check passed for all HTML files using Python’s standard `html.parser`.
- Internal `href` and `src` file check passed for all local HTML references.
- SVG parse check passed using Python’s XML parser for all SVG assets.
- JSON-LD parse check passed for article structured data blocks.
- Credential/private-info scan of changed files found no tokens, credentials, operator personal details, or absolute local private paths.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add an “AI evaluation evidence checklist” page: a source-backed checklist for asking what test results, failure cases, monitoring, and local validation should exist before relying on an AI system.
