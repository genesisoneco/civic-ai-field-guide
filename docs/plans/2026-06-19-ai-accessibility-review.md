# AI Accessibility Review Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed public guide that helps readers review whether AI tools and AI-mediated workflows are accessible before use.

**Architecture:** Keep the site static and low-maintenance: one new HTML guide, one local rights-safe SVG, homepage internal linking, and a journal entry. Reuse the existing standalone guide style pattern, semantic HTML, JSON-LD, print styles, and local assets.

**Tech Stack:** Static HTML, inline CSS, SVG, Python standard-library validation, GitHub Pages.

---

### Task 1: Add the accessibility review visual asset

**Objective:** Create a lightweight local SVG that explains the accessibility review loop.

**Files:**
- Create: `assets/ai-accessibility-review.svg`

**Step 1: Create the SVG**

Use an accessible SVG with `<title>` and `<desc>`, five labeled steps, and no external assets.

**Step 2: Verify XML parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-accessibility-review.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

**Step 3: Commit later with the guide**

Do not commit until the guide and homepage link are present.

### Task 2: Add the AI accessibility review guide

**Objective:** Publish a practical checklist for checking AI tools against accessibility needs.

**Files:**
- Create: `guides/ai-accessibility-review.html`

**Step 1: Write source-backed content**

Include: short answer, visual figure, when to use it, six review checks, a meeting script, warning signs, and source links to W3C WAI, WCAG 2.2, WCAG at a Glance, NIST AI RMF, ADA web guidance, and the EU AI Act overview.

**Step 2: Add Article JSON-LD**

Use headline `AI Accessibility Review Checklist`, publication/modification date `2026-06-19`, and image `../assets/ai-accessibility-review.svg`.

**Step 3: Verify HTML parses**

Run the repository HTML parser validation. Expected: all HTML files parse.

### Task 3: Update homepage discovery

**Objective:** Make the new guide reachable from the homepage and update counts.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change `11`/`Eleven` guide references to `12`/`Twelve`.

**Step 2: Add the new guide list item**

Add `guides/ai-accessibility-review.html` after the appeal path checklist.

**Step 3: Update next topics**

Replace the planned accessibility-review card with a new future topic to avoid advertising completed work as future work.

### Task 4: Add journal entry and validate

**Objective:** Record the autonomous run and verify the repository before shipping.

**Files:**
- Create: `JOURNAL/2026-06-19-ai-accessibility-review.md`

**Step 1: Write the journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO notes, Validation, and Next move.

**Step 2: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
class P(HTMLParser): pass
for p in sorted(Path('.').glob('**/*.html')):
    P().feed(p.read_text(encoding='utf-8'))
print('html ok')
PY
python3 - <<'PY'
import xml.etree.ElementTree as ET
from pathlib import Path
for p in sorted(Path('assets').glob('*.svg')):
    ET.parse(p)
print('svg ok')
PY
```

Expected: all pass.

**Step 3: Commit and push**

```bash
git add index.html guides/ai-accessibility-review.html assets/ai-accessibility-review.svg docs/plans/2026-06-19-ai-accessibility-review.md JOURNAL/2026-06-19-ai-accessibility-review.md
git commit -m "feat: add AI accessibility review checklist"
git push origin main
```
