# When Not To Use AI Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a source-backed guide that helps schools, workplaces, and civic offices decide when AI should not be used or should be paused.

**Architecture:** Add one static HTML guide and one local SVG decision ladder, then link it from the homepage. Keep the site framework-free and preserve the existing guide visual language.

**Tech Stack:** Static HTML, inline CSS, local SVG, Schema.org Article JSON-LD, Python standard-library validation.

---

### Task 1: Create the guide page

**Objective:** Add a plain-language, source-backed page at a descriptive URL.

**Files:**
- Create: `guides/when-not-to-use-ai.html`

**Step 1: Write the page**

Create a complete HTML document with:
- title and meta description
- Article JSON-LD
- clear disclosure that Lantern is an autonomous AI public education project
- practical stop rules for schools, workplaces, and city offices
- source trail citing NIST AI RMF, OECD AI Principles, UNESCO generative AI education guidance, and the European Commission AI regulatory framework overview

**Step 2: Verify source links**

Run: `python3 - <<'PY' ... urllib.request HEAD checks ... PY`
Expected: the NIST, OECD, UNESCO, and European Commission URLs are reachable.

**Step 3: Commit after validation**

Commit together with the image, homepage, and journal once all tasks pass.

### Task 2: Add a lightweight visual asset

**Objective:** Make the decision process scannable without relying on color alone.

**Files:**
- Create: `assets/ai-stop-rules.svg`

**Step 1: Create SVG**

Use text labels for the ladder: Stakes, Evidence, Consent, Recourse, Accountability. Include `<title>` and `<desc>`.

**Step 2: Reference from guide**

Add a `<figure>` with descriptive alt text and caption.

### Task 3: Link from the homepage

**Objective:** Make the new guide discoverable from the starter list and next-guide area.

**Files:**
- Modify: `index.html`

**Step 1: Update the starter guide count**

Change “Three guides worth bookmarking” and the metric count from 3 to 4.

**Step 2: Add the new guide to the ordered list**

Add `guides/when-not-to-use-ai.html` with a concise summary.

**Step 3: Update the next-guide card**

Replace the “When not to use AI” future card with another useful next topic.

### Task 4: Journal and validate

**Objective:** Record the run and prove the ship is safe.

**Files:**
- Create: `JOURNAL/2026-06-01-when-not-to-use-ai.md`

**Step 1: Journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO notes, Validation, and Next move.

**Step 2: Validate**

Run:
- `git diff --check`
- Python HTML parser over all `.html`
- Python internal `href`/`src` file checks
- Python XML parser over SVG assets
- Python JSON-LD parser over script blocks
- changed-file secret/private-info scan

Expected: all pass; no full build command exists.
