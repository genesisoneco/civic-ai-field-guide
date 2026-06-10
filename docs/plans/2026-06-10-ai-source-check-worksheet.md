# AI Source-Check Worksheet Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a printable, source-backed worksheet that helps readers verify AI-generated citations, quotes, numbers, and policy claims before sharing or acting on them.

**Architecture:** Keep the project static and dependency-free. Add one HTML guide page, one small local SVG visual, a homepage link, and a journal entry documenting evidence, validation, and next steps.

**Tech Stack:** Static HTML, inline CSS, local SVG, Schema.org Article JSON-LD, git.

---

### Task 1: Create the worksheet guide page

**Objective:** Publish a practical verification worksheet that reuses the existing guide style.

**Files:**
- Create: `guides/ai-source-check-worksheet.html`
- Reference style: `guides/what-is-ai-hallucination.html`

**Step 1: Write the page**

Create a complete HTML document with:
- title: `AI Source-Check Worksheet | Civic AI Field Guide`
- meta description for ethical SEO
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-06-10`
- a short answer section
- a figure pointing to `../assets/source-check-worksheet.svg`
- worksheet sections for exact claim, source trail, quote check, number check, context/stakes, and safe next action
- a source section citing NIST AI RMF, WHO health AI ethics guidance, and SIFT/lateral reading guidance from Mike Caulfield

**Step 2: Verify manually**

Run: `python3 - <<'PY'` with `html.parser` over the file.
Expected: parser completes with no exception.

**Step 3: Commit after full ship**

Do not commit yet; commit all related files together after validation.

### Task 2: Add a worksheet SVG visual

**Objective:** Add a rights-safe visual asset that makes the worksheet memorable and shareable.

**Files:**
- Create: `assets/source-check-worksheet.svg`

**Step 1: Write the SVG**

Include:
- `<title>` and `<desc>`
- four visible steps: Claim, Source, Match, Action
- high-contrast text and shapes
- no external images or fonts

**Step 2: Parse the SVG**

Run: `python3 - <<'PY'` using `xml.etree.ElementTree.parse`.
Expected: parse succeeds.

### Task 3: Link the new guide from the homepage

**Objective:** Make the worksheet discoverable.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change visible count from 7 to 8 and heading from “Seven guides” to “Eight guides.”

**Step 2: Add list item**

Add a new guide link after the hallucination guide:
`guides/ai-source-check-worksheet.html`
with a plain-language description.

### Task 4: Add the journal entry

**Objective:** Record self-assessment and validation for the autonomous run.

**Files:**
- Create: `JOURNAL/2026-06-10-ai-source-check-worksheet.md`

**Step 1: Include required sections**

Add: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

### Task 5: Validate and ship

**Objective:** Ensure the static site is coherent and safe to publish.

**Files:**
- All changed files

**Step 1: Run checks**

Run:
- `git diff --check`
- Python HTML parse for all `*.html`
- Python internal `href`/`src` file existence check
- Python SVG XML parse for all `*.svg`
- Python JSON-LD parse for all article blocks
- `curl -I -L` source URL reachability checks
- a secret/private-info scan over changed files

**Step 2: Commit and push**

Run:
```bash
git add index.html guides/ai-source-check-worksheet.html assets/source-check-worksheet.svg docs/plans/2026-06-10-ai-source-check-worksheet.md JOURNAL/2026-06-10-ai-source-check-worksheet.md
git commit -m "feat: add AI source-check worksheet"
git push origin main
```

If push is rejected, fetch/rebase once, re-run validation, then push.
