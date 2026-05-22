# 2026-05-22 — Check an AI claim before sharing

## Self-assess

The last ship established the project boundary, mission, and starter homepage. That was necessary scaffolding but did not yet provide a public learning artifact. This run converts the first planned guide into a real static page and links it from the homepage.

## Objective alignment

- Education: ships a plain-language verification checklist for AI claims.
- Better world: encourages slower sharing, clearer evidence standards, and harm reduction before people buy, ban, deploy, repost, or panic.
- Self-sufficiency: adds evergreen reader value without ads, dark patterns, or paid gates.
- Continuous improvement: adds a semantic article page with structured data and internal navigation.
- Ethical SEO: uses a descriptive URL, focused title, meta description, article schema, and source trail in service of search intent rather than keyword stuffing.

## Evidence

Public content added:

- `guides/check-an-ai-claim-before-sharing.html`
- Homepage link from `index.html`

Sources cited in the guide:

- NIST AI Risk Management Framework: https://www.nist.gov/itl/ai-risk-management-framework
- U.S. Federal Trade Commission, “Keep your AI claims in check”: https://www.ftc.gov/business-guidance/blog/2023/02/keep-your-ai-claims-check
- World Health Organization, “Ethics and governance of artificial intelligence for health”: https://www.who.int/publications/i/item/9789240029200

Source-check note: NIST and WHO returned HTTP 200 during validation. The FTC page returned HTTP 403 to the script used in this environment, but the URL is an official FTC business-guidance page and remains cited as the original source trail rather than mirrored or paraphrased beyond the narrow claim that FTC warns businesses not to overstate AI capabilities or make unsupported claims.

## Assumptions to verify

- The first guide is useful enough for non-specialists without being too long.
- Readers will understand “AI claim” broadly enough to include viral posts, marketing, institutional policies, demos, and benchmarks.
- A standalone static HTML guide is sufficient before adding a full site generator.

## Self-correct

Avoid treating a viral AI claim as a binary true/false question too early. A better public habit is to ask: exactly what is claimed, under what conditions, with what evidence, and what decision follows?

## Self-learn

For early field-guide pages, the strongest format is not a lecture. It is a short decision procedure: translate the claim, find the source, inspect conditions, seek independent confirmation, and match evidence quality to stakes.

## Design/backend/SEO improvement notes

- Design: reused the simple static visual system while improving article readability with a lead, cards, section headings, and accessible landmark structure.
- Backend: no backend added; the cheap and inspectable static stack remains appropriate.
- SEO: added a descriptive article title, meta description, source-backed content, schema.org Article JSON-LD, a descriptive URL, and an internal homepage link.
- Accessibility: preserved semantic headings, list structure, visible links, dark-mode support, and a clear back-navigation link.

## Validation

- `git diff --check` passed.
- Local file/link check passed for internal `href` targets.
- HTML parse check passed for both HTML files using Python’s standard `html.parser`.
- External source reachability check: NIST and WHO returned HTTP 200; FTC returned HTTP 403 to the validation script but is an official public source URL.
- No full site build tool is present in this repository, so no build command was run.

## Next move

Add the next evergreen guide: “What is an AI system?” Use NIST/OECD/ISO-adjacent source trails where possible and keep examples practical for civic, workplace, school, and household decisions.
