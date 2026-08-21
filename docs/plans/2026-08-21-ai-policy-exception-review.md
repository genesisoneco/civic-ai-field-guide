# AI Policy Exception Review Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed field guide page that helps civic teams decide whether a temporary AI policy exception should close, renew, narrow, escalate, or become formal policy.

**Architecture:** Keep the site static and consistent with existing guide pages. Add one HTML guide, one rights-safe local SVG, one homepage entry, and one journal note documenting evidence, validation, and next steps.

**Tech Stack:** Static HTML/CSS, inline JSON-LD, local SVG, Python validation scripts, git.

---

### Task 1: Add the public guide page

**Objective:** Create a copy-pasteable AI policy exception review guide with citations and safe public-record language.

**Files:**
- Create: `guides/ai-policy-exception-review.html`
- Reference style: `guides/ai-oversight-calendar.html`

**Step 1: Write the page**

Create `guides/ai-policy-exception-review.html` with:
- Title: `AI Policy Exception Review | Civic AI Field Guide`
- Meta description: `A practical review for deciding whether a temporary AI policy exception should close, renew, narrow, escalate, or become formal policy.`
- JSON-LD Article block with datePublished/dateModified `2026-08-21`
- Sections: short answer, why it matters, decision table, before review, review questions, decision template, stop rules, related pages, sources.
- Citations to NIST AI RMF, OMB M-24-10, and CISA Secure by Design.

**Step 2: Verify the page parses**

Run: `python3 - <<'PY' ... HTMLParser check ... PY`
Expected: PASS — no parser exceptions.

**Step 3: Commit later with the full ship**

Do not commit this task alone; commit after index, image, journal, and validation are complete.

### Task 2: Add a rights-safe visual asset

**Objective:** Add a small local SVG that explains the exception decision path.

**Files:**
- Create: `assets/ai-policy-exception-review.svg`
- Modify: `guides/ai-policy-exception-review.html` to reference the SVG with descriptive alt text and a caption.

**Step 1: Create the SVG**

Create an accessible SVG with `<title>` and `<desc>` showing five outcomes: close, renew briefly, narrow, escalate, formalize.

**Step 2: Verify XML**

Run: `python3 - <<'PY' ... ElementTree parse assets/*.svg ... PY`
Expected: PASS — all SVG files parse.

### Task 3: Update homepage discovery

**Objective:** Add the new guide to the homepage and update counts/next-topic cards.

**Files:**
- Modify: `index.html`

**Step 1: Update count text**

Change `38` starter guides and `Thirty-eight guides` to `39` / `Thirty-nine guides`.

**Step 2: Add list item**

Add a new list item after `AI oversight calendar` linking to `guides/ai-policy-exception-review.html`.

**Step 3: Refresh next guides**

Replace the now-shipped next-topic card with another useful next idea, such as `AI policy meeting agenda` and `AI public comment review`.

### Task 4: Add the journal entry

**Objective:** Document self-assessment, evidence, assumptions, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-08-21-ai-policy-exception-review.md`

**Step 1: Write the journal**

Include required headings: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Include source-check status**

Record that cited source URLs returned HTTP 200 from this environment.

### Task 5: Validate and ship

**Objective:** Ensure the static site is coherent, safe, and pushed.

**Files:**
- All changed files.

**Step 1: Run whitespace validation**

Run: `git diff --check`
Expected: no output and exit 0.

**Step 2: Run link and parse checks**

Run Python checks for HTML parsing, JSON-LD parsing, internal `href`/`src` targets, and SVG XML parsing.
Expected: all checks pass.

**Step 3: Scan changed files for private data**

Run a conservative changed-file scan for tokens, credentials, local private paths, logs, and secrets.
Expected: no private operator info or credentials found.

**Step 4: Commit and push**

Run:
```bash
git add index.html guides/ai-policy-exception-review.html assets/ai-policy-exception-review.svg docs/plans/2026-08-21-ai-policy-exception-review.md JOURNAL/2026-08-21-ai-policy-exception-review.md
git commit -m "feat: add AI policy exception review"
git push origin main
```
Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, and push again.
