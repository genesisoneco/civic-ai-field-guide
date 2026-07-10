# AI Public Notice Template Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language guide that helps organizations tell people when AI is used in a workflow, what it affects, who owns it, and how to reach human review or accessibility/language support.

**Architecture:** Keep the project static and dependency-free. Add one HTML guide, one local SVG visual, homepage guide count/link updates, and one journal entry. Reuse the existing guide pattern: inline CSS, semantic headings, Article JSON-LD, accessible figure, checklist/table content, source links, and print styles.

**Tech Stack:** Static HTML, inline CSS, local SVG, schema.org Article JSON-LD, Python standard-library validation.

---

### Task 1: Create the public notice guide shell

**Objective:** Add a new HTML guide with metadata, layout, and a source-ready structure.

**Files:**
- Create: `guides/ai-public-notice-template.html`

**Step 1: Write the static page shell**

Create `guides/ai-public-notice-template.html` with:
- `<title>AI Public Notice Template | Civic AI Field Guide</title>`
- a meta description about telling people when AI is used and how to get human review
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-07-10`
- semantic sections for short answer, when notice is needed, a starter template, plain-language fields, accessibility/language access, bad signs, checklist, and sources

**Step 2: Verify parse**

Run: `python3 - <<'PY' ... HTMLParser ... PY`
Expected: PASS for `guides/ai-public-notice-template.html`.

**Step 3: Commit-ready checkpoint**

Do not commit yet; complete the content, asset, homepage, and journal first so the ship is cohesive.

### Task 2: Add source-backed notice guidance

**Objective:** Fill the guide with practical notice language and caveats without claiming legal compliance.

**Files:**
- Modify: `guides/ai-public-notice-template.html`

**Step 1: Add content grounded in sources**

Include guidance based on:
- NIST AI RMF governance, mapping, measuring, managing, transparency, documentation, and accountability themes
- OMB M-24-10 public-sector AI governance expectations, especially rights/safety-impacting uses and public inventories/notice concepts
- European Commission AI Act overview for transparency and high-risk obligations at a high level
- ICO AI and data protection guidance for transparency/accountability when personal data is involved
- WCAG 2.2 for accessible notice presentation

**Step 2: Run source reachability check**

Run an inline Python `urllib.request` loop for all cited URLs.
Expected: HTTP 200 for reachable sources; document any non-200 in the journal.

### Task 3: Add a rights-safe SVG visual

**Objective:** Add a lightweight local diagram that explains what a useful AI notice connects.

**Files:**
- Create: `assets/ai-public-notice-template.svg`

**Step 1: Create SVG**

Add a simple diagram with `<title>` and `<desc>` showing notice connected to purpose, AI role, owner, human review, appeal/contact, language access, disability access, and correction path.

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

Change starter guide count from `20` to `21` and heading from `Twenty guides worth bookmarking.` to `Twenty-one guides worth bookmarking.`

**Step 2: Add guide list item**

Add a new list item after `AI system owner checklist` linking to `guides/ai-public-notice-template.html` with a short description.

**Step 3: Update next-guide cards**

Remove the now-completed public notice card and replace it with a useful future topic such as `AI policy meeting agenda` or `AI data minimization checklist`.

### Task 5: Add journal entry and validate

**Objective:** Record the ship, validation, self-assessment, and next move.

**Files:**
- Create: `JOURNAL/2026-07-10-ai-public-notice-template.md`

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
git add guides/ai-public-notice-template.html assets/ai-public-notice-template.svg index.html docs/plans/2026-07-10-ai-public-notice-template.md JOURNAL/2026-07-10-ai-public-notice-template.md
git commit -m "feat: add AI public notice template"
git push origin main
```

If push is rejected, fetch/rebase once, re-run validation, then push. Do not force-push.
