# AI Data Minimization Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language checklist that helps teams collect less personal data, retain it for less time, and reduce privacy exposure before adding AI to a workflow.

**Architecture:** Keep the project static and dependency-free. Add one HTML guide, one local SVG visual, homepage guide count/link updates, and one journal entry. Reuse the existing guide pattern: inline CSS, semantic headings, Article JSON-LD, accessible figure, checklist/table content, source links, and print styles.

**Tech Stack:** Static HTML, inline CSS, local SVG, schema.org Article JSON-LD, Python standard-library validation.

---

### Task 1: Create the data minimization guide shell

**Objective:** Add a new HTML guide with metadata, layout, and a source-ready structure.

**Files:**
- Create: `guides/ai-data-minimization-checklist.html`

**Step 1: Write the static page shell**

Create `guides/ai-data-minimization-checklist.html` with:
- `<title>AI Data Minimization Checklist | Civic AI Field Guide</title>`
- a meta description about collecting less personal data, retaining it for less time, and reducing privacy risk before AI use
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-07-13`
- semantic sections for short answer, why it matters, first-pass checklist, minimization points, practical patterns, bad signs, starter policy language, and sources

**Step 2: Verify parse**

Run: `python3 - <<'PY' ... HTMLParser ... PY`
Expected: PASS for `guides/ai-data-minimization-checklist.html`.

**Step 3: Commit-ready checkpoint**

Do not commit yet; complete the content, asset, homepage, and journal first so the ship is cohesive.

### Task 2: Add source-backed minimization guidance

**Objective:** Fill the guide with practical privacy-risk reduction language and caveats without claiming legal compliance.

**Files:**
- Modify: `guides/ai-data-minimization-checklist.html`

**Step 1: Add content grounded in sources**

Include guidance based on:
- NIST Privacy Framework risk-management functions
- ICO data minimisation principle: adequate, relevant, limited to what is necessary
- NIST AI RMF governance, mapping, measuring, managing, transparency, documentation, and accountability themes
- OMB M-24-10 public-sector AI governance expectations, especially rights/safety-impacting uses
- WCAG 2.2 for accessible presentation

**Step 2: Run source reachability check**

Run an inline Python `urllib.request` loop for all cited URLs.
Expected: HTTP 200 for reachable sources; document any non-200 in the journal.

### Task 3: Add a rights-safe SVG visual

**Objective:** Add a lightweight local diagram that explains the data minimization path.

**Files:**
- Create: `assets/ai-data-minimization-checklist.svg`

**Step 1: Create SVG**

Add a simple funnel diagram with `<title>` and `<desc>` showing purpose, necessary fields, redaction/protection, short retention, limited access, and deletion review.

**Step 2: Reference it from the guide**

Add an `<img>` with descriptive `alt` text and a caption.

**Step 3: Validate XML**

Run: `python3 - <<'PY' ... xml.etree.ElementTree.parse(...) ... PY`
Expected: PASS for the new SVG and all existing SVGs.

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable and update counts accurately.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count and heading**

Change starter guide count from `21` to `22` and heading from `Twenty-one guides worth bookmarking.` to `Twenty-two guides worth bookmarking.`

**Step 2: Add guide list item**

Add a new list item after `AI public notice template` linking to `guides/ai-data-minimization-checklist.html` with a short description.

**Step 3: Update next-guide cards**

Remove the now-completed data minimization card and replace it with a useful future topic such as `AI record retention schedule`.

### Task 5: Add journal entry and validate

**Objective:** Record the ship, validation, self-assessment, and next move.

**Files:**
- Create: `JOURNAL/2026-07-13-ai-data-minimization-checklist.md`

**Step 1: Write journal entry**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

**Step 2: Run validation**

Run:
```bash
git diff --check
python3 - <<'PY'
# HTML parse, local href/src check, SVG XML parse, JSON-LD parse
PY
python3 - <<'PY'
# scan changed files for token/secret/private-path patterns
PY
```
Expected: all checks pass. Note that no full site build tool is present if applicable.

**Step 3: Commit and push**

```bash
git add guides/ai-data-minimization-checklist.html assets/ai-data-minimization-checklist.svg index.html docs/plans/2026-07-13-ai-data-minimization-checklist.md JOURNAL/2026-07-13-ai-data-minimization-checklist.md
git commit -m "feat: add AI data minimization checklist"
git push origin main
```

If push is rejected, fetch/rebase once, re-run validation, then push. Do not force-push.
