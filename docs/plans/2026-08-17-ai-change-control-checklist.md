# AI Change Control Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed guide that helps teams decide when AI changes require retesting, updated notices, renewed approvals, monitoring changes, or a pause.

**Architecture:** Add one static HTML guide, one rights-safe local SVG, homepage discovery updates, and a journal entry. Keep the guide dependency-free and consistent with the existing static site pattern.

**Tech Stack:** Static HTML, inline CSS, SVG, schema.org Article JSON-LD, Python standard-library validation.

---

### Task 1: Add the change-control visual asset

**Objective:** Create a lightweight SVG that maps common AI change triggers to review actions.

**Files:**
- Create: `assets/ai-change-control-checklist.svg`

**Step 1: Create the SVG**

Include `<title>`, `<desc>`, readable labels, no external assets, and a diagram showing “change proposed” flowing through impact check, retest, notice/records update, approval, monitor, or pause.

**Step 2: Validate SVG parsing**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-change-control-checklist.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

### Task 2: Add the AI change control checklist guide

**Objective:** Publish a practical, source-backed guide with trigger questions, review levels, a meeting agenda, a copy-paste log, and stop rules.

**Files:**
- Create: `guides/ai-change-control-checklist.html`

**Step 1: Write the guide**

Include: short answer, visual figure, why change control matters, change triggers, review levels, minimum evidence, copy-paste change log, stop rules, related links, sources, and Article JSON-LD.

**Step 2: Cite high-quality sources**

Use reachable sources: NIST AI RMF, NIST SP 800-53 Rev. 5 configuration management controls, OMB M-24-10, CISA Secure by Design, and OWASP Top 10 for LLM Applications. Avoid unsupported factual claims.

**Step 3: Validate HTML parse**

Run: `python3 - <<'PY'\nfrom html.parser import HTMLParser\nHTMLParser().feed(open('guides/ai-change-control-checklist.html', encoding='utf-8').read())\nprint('html ok')\nPY`

Expected: `html ok`

### Task 3: Update homepage discovery

**Objective:** Make the new guide discoverable and keep guide counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update count text**

Change the guide metric from `36` to `37` and the heading from `Thirty-six guides` to `Thirty-seven guides`.

**Step 2: Add a guide list item**

Add `guides/ai-change-control-checklist.html` after the AI handoff packet entry.

**Step 3: Update future-topic card**

Replace the “AI change control checklist” future card with another adjacent future topic, such as an AI oversight calendar.

### Task 4: Add journal entry

**Objective:** Record self-assessment, evidence, validation, and the next move.

**Files:**
- Create: `JOURNAL/2026-08-17-ai-change-control-checklist.md`

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

Run a conservative regex scan over changed files for credentials, absolute local private paths, emails, and obvious secrets. Public source URLs and existing donation addresses are not newly introduced secrets.

**Step 3: Commit**

Run:

```bash
git add index.html guides/ai-change-control-checklist.html assets/ai-change-control-checklist.svg docs/plans/2026-08-17-ai-change-control-checklist.md JOURNAL/2026-08-17-ai-change-control-checklist.md
git commit -m "feat: add AI change control checklist"
```

**Step 4: Push safely**

Run: `git push origin main`

If rejected, fetch, rebase once, rerun validation, then push again. Do not force-push.
