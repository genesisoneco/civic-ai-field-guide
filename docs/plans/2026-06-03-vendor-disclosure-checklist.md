# Vendor Disclosure Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language checklist that helps schools, public agencies, and workplaces ask AI vendors for enough evidence before adoption.

**Architecture:** Keep the project static and inspectable: one new HTML guide, one local SVG visual asset, one homepage internal link, and one run journal. Reuse existing guide-page CSS patterns so the page stays consistent without adding a build system.

**Tech Stack:** Static HTML, inline CSS, local SVG, JSON-LD Article structured data, Python standard-library validation.

---

### Task 1: Add the vendor disclosure guide

**Objective:** Create a public guide with concrete vendor questions, source trail, and no legal/procurement advice claims.

**Files:**
- Create: `guides/vendor-disclosure-checklist.html`

**Step 1: Write the page**

Create a static HTML page containing:
- Title: `AI Vendor Disclosure Checklist`
- Metadata and Article JSON-LD
- A short answer section
- A figure using `../assets/vendor-disclosure-map.svg`
- Checklist sections for purpose, evidence, data, oversight, access, security, incidents, contract guardrails, and a sendable email template
- Source links to NIST AI RMF, OMB M-24-10, UK AI procurement guidance, OECD AI Principles, EU AI regulatory framework, and CISA Secure by Design

**Step 2: Verify structure**

Run: `python3 -m html.parser guides/vendor-disclosure-checklist.html`
Expected: no parse exception.

**Step 3: Commit checkpoint**

```bash
git add guides/vendor-disclosure-checklist.html
git commit -m "feat: add AI vendor disclosure checklist"
```

### Task 2: Add a rights-safe visual asset

**Objective:** Add a lightweight SVG that visually summarizes the evidence flow a buyer should request from an AI vendor.

**Files:**
- Create: `assets/vendor-disclosure-map.svg`

**Step 1: Create SVG**

Create a local SVG with `<title>` and `<desc>`, six labeled cards, and no external image dependencies.

**Step 2: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/vendor-disclosure-map.svg')\nPY`
Expected: no output.

**Step 3: Commit checkpoint**

```bash
git add assets/vendor-disclosure-map.svg
git commit -m "feat: add vendor disclosure visual"
```

### Task 3: Add homepage discovery link

**Objective:** Make the new guide discoverable from the homepage starter list.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count and list**

Change “Four guides worth bookmarking” to “Five guides worth bookmarking,” update the metric from `4` to `5`, and add a fifth ordered-list item linking to `guides/vendor-disclosure-checklist.html`.

**Step 2: Verify local links**

Run the repository local link checker from validation.
Expected: no missing local `href` or `src` targets.

**Step 3: Commit checkpoint**

```bash
git add index.html
git commit -m "feat: link vendor disclosure checklist from homepage"
```

### Task 4: Add run journal and validation

**Objective:** Record the self-assessment, evidence, assumptions, and validation for the autonomous ship.

**Files:**
- Create: `JOURNAL/2026-06-03-vendor-disclosure-checklist.md`

**Step 1: Write journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

**Step 2: Run final validation**

Run:
```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
for p in Path('.').glob('**/*.html'):
    HTMLParser().feed(p.read_text(encoding='utf-8'))
print('html ok')
PY
```
Run local link, SVG parse, JSON-LD parse, source reachability, and secret scans.

**Step 3: Commit and push**

```bash
git add JOURNAL/2026-06-03-vendor-disclosure-checklist.md docs/plans/2026-06-03-vendor-disclosure-checklist.md guides/vendor-disclosure-checklist.html assets/vendor-disclosure-map.svg index.html
git commit -m "feat: add AI vendor disclosure checklist"
git push origin main
```

If push is rejected, fetch/rebase once, rerun validation, then push.
