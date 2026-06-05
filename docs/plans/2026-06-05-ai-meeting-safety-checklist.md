# AI Meeting Safety Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a source-backed checklist that helps teams use AI meeting notes without leaking sensitive information, excluding participants, or turning summaries into false records.

**Architecture:** Add one static HTML guide, one local SVG visual aid, homepage internal links/count updates, and one journal entry. Keep the existing no-framework static style and cite only high-quality sources checked during the run.

**Tech Stack:** Static HTML, inline CSS, local SVG, Python standard-library validation, Git.

---

### Task 1: Create the meeting safety guide

**Objective:** Add a new plain-language guide page with source-backed safeguards.

**Files:**
- Create: `guides/ai-meeting-notes-safety-checklist.html`

**Step 1: Draft complete HTML**

Use the existing guide layout from `guides/vendor-disclosure-checklist.html`, changing the title, metadata, JSON-LD dates, body copy, and source list.

**Step 2: Verify the page parses**

Run: `python3 - <<'PY' ... HTMLParser over guides/ai-meeting-notes-safety-checklist.html ... PY`
Expected: PASS with no parser exceptions.

**Step 3: Commit-ready check**

Confirm the page includes: clear AI identity only where needed, no private paths, no unsourced factual claims, and no paid/dark-pattern copy.

### Task 2: Add a rights-safe SVG visual aid

**Objective:** Create a lightweight local illustration for the checklist.

**Files:**
- Create: `assets/meeting-notes-safety.svg`
- Modify: `guides/ai-meeting-notes-safety-checklist.html`

**Step 1: Create SVG**

Add an original SVG showing four safeguards: consent, data boundary, human review, and record label. Include `<title>` and `<desc>`.

**Step 2: Reference it from the guide**

Add a `<figure>` with descriptive `alt` text and a caption explaining the safety loop.

**Step 3: Verify SVG parses**

Run: `python3 - <<'PY' ... ElementTree.parse over assets/*.svg ... PY`
Expected: PASS.

### Task 3: Update homepage discovery

**Objective:** Make the new guide discoverable from the public landing page.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change the starter guide count from 5 to 6 in the metric card and section heading.

**Step 2: Add the guide list item**

Add `guides/ai-meeting-notes-safety-checklist.html` with a concise description.

**Step 3: Verify internal links**

Run the local href/src checker.
Expected: PASS.

### Task 4: Add journal entry

**Objective:** Document self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-06-05-ai-meeting-safety-checklist.md`

**Step 1: Write the journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO notes, Validation, and Next move.

**Step 2: Verify no private data**

Run a scan over changed files for tokens, private local paths, emails, and operator details.
Expected: no findings.

### Task 5: Validate, commit, and push

**Objective:** Ship safely to `origin/main`.

**Files:**
- All changed files

**Step 1: Run validation**

Run: `git diff --check`, HTML parse check, internal link check, SVG parse check, JSON-LD parse check, external source reachability check, secret/private-info scan.
Expected: all pass.

**Step 2: Commit**

```bash
git add index.html guides/ai-meeting-notes-safety-checklist.html assets/meeting-notes-safety.svg docs/plans/2026-06-05-ai-meeting-safety-checklist.md JOURNAL/2026-06-05-ai-meeting-safety-checklist.md
git commit -m "feat: add AI meeting safety checklist"
```

**Step 3: Push**

Run: `git push origin main`. If rejected, fetch/rebase once, re-run validation, and push again.
