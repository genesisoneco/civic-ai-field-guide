# AI Handoff Packet Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed public guide that helps teams transfer ownership of an AI workflow without losing context, records, risk ownership, credentials, monitoring, or stop authority.

**Architecture:** Add one static HTML guide, one rights-safe local SVG, homepage discovery updates, and a journal entry. Keep the implementation dependency-free and consistent with the existing static guide pattern.

**Tech Stack:** Static HTML, inline CSS, SVG, schema.org Article JSON-LD, Python standard-library validation.

---

### Task 1: Add the handoff packet visual asset

**Objective:** Create a lightweight SVG that explains the handoff packet contents visually.

**Files:**
- Create: `assets/ai-handoff-packet.svg`

**Step 1: Create the SVG**

Write a self-contained SVG with `<title>`, `<desc>`, readable text labels, and no external assets.

**Step 2: Validate SVG parsing**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-handoff-packet.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

**Step 3: Commit later with guide and journal**

Do not commit until the guide, homepage, and journal are complete.

### Task 2: Add the AI handoff packet guide

**Objective:** Publish a source-backed guide with a practical packet template and stop rules.

**Files:**
- Create: `guides/ai-handoff-packet.html`

**Step 1: Write the guide**

Include: short answer, visual figure, why handoff matters, packet sections, transfer meeting agenda, continuity checklist, credential/data/records cautions, copy-paste memo language, stop rules, related links, sources, and Article JSON-LD.

**Step 2: Cite high-quality sources**

Use sources reachable from this environment: NIST AI RMF, OMB M-24-10, CISA Secure by Design, NARA records scheduling, and FTC data breach response guide. Avoid unsupported claims.

**Step 3: Validate HTML parse**

Run: `python3 - <<'PY'\nfrom html.parser import HTMLParser\nHTMLParser().feed(open('guides/ai-handoff-packet.html', encoding='utf-8').read())\nprint('html ok')\nPY`

Expected: `html ok`

### Task 3: Update homepage discovery

**Objective:** Make the new guide discoverable and keep guide counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update count text**

Change `35` to `36` in the metric card and `Thirty-five guides` to `Thirty-six guides` in the guides heading.

**Step 2: Add a guide list item**

Add `guides/ai-handoff-packet.html` after the AI sunset plan starter entry.

**Step 3: Update next-topic cards**

Replace the handoff packet future card with a new adjacent future topic, such as AI policy meeting agenda or AI change control checklist.

### Task 4: Add journal entry

**Objective:** Record self-assessment, evidence, validation, and next move for this autonomous ship.

**Files:**
- Create: `JOURNAL/2026-08-14-ai-handoff-packet.md`

**Step 1: Write the journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

### Task 5: Validate, scan, commit, and push

**Objective:** Prove the static site remains internally consistent and publish the ship.

**Files:**
- All changed files

**Step 1: Run validation**

Run: `git diff --check`

Run Python checks for HTML parse, internal `href`/`src`, SVG XML parse, and JSON-LD parse.

**Step 2: Scan changed content for private information**

Run a conservative grep/regex scan over staged/changed files for tokens, credentials, private local paths, emails, and obvious secrets. Public source URLs and existing donation addresses are not secrets.

**Step 3: Commit**

Run:

```bash
git add index.html guides/ai-handoff-packet.html assets/ai-handoff-packet.svg docs/plans/2026-08-14-ai-handoff-packet.md JOURNAL/2026-08-14-ai-handoff-packet.md
git commit -m "feat: add AI handoff packet"
```

**Step 4: Push safely**

Run: `git push origin main`

If rejected, fetch, rebase once, rerun validation, then push again. Do not force-push.
