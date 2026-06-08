# AI Hallucination Guide Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed plain-language guide explaining AI hallucination as a verification and confidence problem with practical checks.

**Architecture:** Keep the static-site pattern: one self-contained HTML guide, one local SVG visual asset, one homepage link, and one journal entry. Avoid new build tooling or JavaScript.

**Tech Stack:** Static HTML, inline CSS, local SVG, schema.org Article JSON-LD, Python validation scripts.

---

### Task 1: Add the guide page

**Objective:** Publish a reader-facing guide that defines hallucination without hype and gives a reusable verification habit.

**Files:**
- Create: `guides/what-is-ai-hallucination.html`

**Step 1: Write the page**

Create a complete static HTML page with:
- Title: `What Is AI Hallucination? | Civic AI Field Guide`
- Meta description focused on practical verification.
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-06-08`.
- A short answer, a verification ladder, examples, red flags, and cited sources.

**Step 2: Verify locally**

Run: `python3 - <<'PY' ... HTMLParser check ... PY`
Expected: PASS for all HTML files.

**Step 3: Commit later with the rest of the ship**

Commit after all related files are complete so the guide, asset, homepage link, and journal stay atomic.

### Task 2: Add a lightweight SVG diagram

**Objective:** Give readers a memorable visual model for checking AI answers.

**Files:**
- Create: `assets/hallucination-check-ladder.svg`

**Step 1: Create the SVG**

Add a rights-safe local SVG with `<title>` and `<desc>` describing a four-step ladder: ask, compare, verify, decide.

**Step 2: Reference it from the guide**

Use an `<img>` with descriptive alt text and a caption explaining the diagram.

**Step 3: Verify SVG parsing**

Run: `python3 - <<'PY' ... ElementTree parse check ... PY`
Expected: PASS for all SVG files.

### Task 3: Add homepage internal link

**Objective:** Make the new guide discoverable from the site landing page.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change the metric and section heading from six to seven guides.

**Step 2: Add a new guide list item**

Add `guides/what-is-ai-hallucination.html` with a short description.

**Step 3: Verify internal links**

Run the local href/src checker.
Expected: all local file references exist.

### Task 4: Add journal entry and validate

**Objective:** Record the self-assessment, evidence, validation, and next move for the autonomous ship.

**Files:**
- Create: `JOURNAL/2026-06-08-ai-hallucination-guide.md`

**Step 1: Write journal entry**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

**Step 2: Run validation**

Run:
```bash
git diff --check
python3 tools-or-inline validation for HTML, local refs, SVG, JSON-LD, and changed-file secret scan
```
Expected: all checks pass; note that no full build tool is present if true.

**Step 3: Commit and push**

```bash
git add guides/what-is-ai-hallucination.html assets/hallucination-check-ladder.svg index.html docs/plans/2026-06-08-ai-hallucination-guide.md JOURNAL/2026-06-08-ai-hallucination-guide.md
git commit -m "feat: add AI hallucination verification guide"
git push origin main
```
