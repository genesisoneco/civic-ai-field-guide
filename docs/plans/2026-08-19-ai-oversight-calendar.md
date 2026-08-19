# AI Oversight Calendar Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a practical, source-backed AI oversight calendar guide that helps civic teams remember recurring review work after launch.

**Architecture:** Keep the project as static HTML with one new guide page, one local SVG visual asset, homepage index updates, and a journal entry. Use existing guide styling patterns so the page is readable, printable, accessible, and cheap to host.

**Tech Stack:** Static HTML, inline CSS, local SVG, Schema.org Article JSON-LD, GitHub Pages-compatible files.

---

### Task 1: Add the guide page

**Objective:** Create a new source-backed guide for recurring AI oversight work.

**Files:**
- Create: `guides/ai-oversight-calendar.html`

**Step 1: Write the page**

Create a static HTML page with:
- title and meta description
- Article JSON-LD
- short answer
- accessible SVG figure reference
- monthly, quarterly, semiannual, annual, and event-triggered checklists
- copy-paste calendar template
- stop rules
- related field-guide links
- source list

**Step 2: Verify page exists**

Run: `test -f guides/ai-oversight-calendar.html`
Expected: exit code 0.

**Step 3: Commit later with the full ship**

This task is part of one small autonomous ship, so commit after validation.

### Task 2: Add the visual asset

**Objective:** Add a rights-safe local diagram that clarifies the oversight rhythm.

**Files:**
- Create: `assets/ai-oversight-calendar.svg`

**Step 1: Create SVG**

Create an SVG with `<title>` and `<desc>` showing monthly checks, quarterly drills, semiannual evidence review, annual renewal/sunset, and event-triggered review.

**Step 2: Verify parseability**

Run: `python3 - <<'PY' ... xml.etree.ElementTree.parse(...) ... PY`
Expected: SVG parse passes.

### Task 3: Update homepage discovery

**Objective:** Link the new guide from the homepage and update guide counts.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change visible guide count from 37 to 38 in hero metric and heading.

**Step 2: Add guide list item**

Add a new list item after AI change control checklist linking to `guides/ai-oversight-calendar.html`.

**Step 3: Refresh next-guide card**

Replace the AI oversight calendar “next guides” card with a new future topic.

### Task 4: Add journal entry

**Objective:** Record self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-08-19-ai-oversight-calendar.md`

**Step 1: Write journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

### Task 5: Validate and ship

**Objective:** Confirm the static site is internally consistent, free of obvious secrets, committed, and pushed.

**Files:**
- Validate changed files and all HTML/SVG references.

**Step 1: Run validation**

Run:
```bash
git diff --check
python3 - <<'PY'
# parse HTML, local links, SVG, JSON-LD
PY
```
Expected: all checks pass.

**Step 2: Scan for private info**

Run a local changed-file scan for token-like strings, private paths, and personal operator details.
Expected: no newly introduced secrets or private operator information.

**Step 3: Commit and push**

Run:
```bash
git add index.html guides/ai-oversight-calendar.html assets/ai-oversight-calendar.svg docs/plans/2026-08-19-ai-oversight-calendar.md JOURNAL/2026-08-19-ai-oversight-calendar.md
git commit -m "feat: add AI oversight calendar"
git push origin main
```
Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, and push again.
