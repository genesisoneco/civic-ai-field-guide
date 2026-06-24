# AI Classroom Policy Starter Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed classroom AI policy starter that helps teachers, students, and school leaders decide when AI use is allowed, limited, cited, or off-limits.

**Architecture:** Keep the site static and auditable: one HTML guide, one local SVG visual asset, homepage internal links, and one journal entry. Reuse the existing guide page pattern for accessibility, print support, JSON-LD, and source lists.

**Tech Stack:** Static HTML, inline CSS, local SVG, Python standard-library validation scripts, Git.

---

### Task 1: Add the classroom policy visual asset

**Objective:** Create a rights-safe local SVG explaining the allowed/limited/cited/off-limits policy lanes.

**Files:**
- Create: `assets/ai-classroom-policy-starter.svg`

**Step 1: Create the SVG**

Add an SVG with `<title>`, `<desc>`, readable labels, and no external image dependencies.

**Step 2: Verify XML parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-classroom-policy-starter.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

**Step 3: Commit later with the guide**

Do not commit until the page and homepage links exist.

---

### Task 2: Add the source-backed guide page

**Objective:** Publish a practical AI classroom policy starter with clear limits, disclosure template, privacy/accessibility guidance, and citations.

**Files:**
- Create: `guides/ai-classroom-policy-starter.html`

**Step 1: Write the page**

Use the existing guide style pattern. Include:
- title and meta description;
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-06-24`;
- a short answer section;
- local SVG figure with descriptive alt text and caption;
- four policy lanes: allowed, limited, cited, off-limits;
- privacy, accessibility, teacher responsibility, disclosure, detector caution, and source sections.

**Step 2: Verify the page parses**

Run: `python3 - <<'PY'\nfrom html.parser import HTMLParser\nHTMLParser().feed(open('guides/ai-classroom-policy-starter.html', encoding='utf-8').read())\nprint('html ok')\nPY`

Expected: `html ok`

---

### Task 3: Update homepage discovery

**Objective:** Make the new guide discoverable from the homepage and update counts.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change `13` to `14` in the starter guide metric and change “Thirteen guides worth bookmarking” to “Fourteen guides worth bookmarking.”

**Step 2: Add guide list item**

Add `guides/ai-classroom-policy-starter.html` after the procurement red flags guide with the description: “A starter policy for deciding when classroom AI use is allowed, limited, cited, or off-limits.”

**Step 3: Update next-guide cards**

Replace the classroom-policy future card with a new next topic so the homepage does not advertise completed work as pending.

---

### Task 4: Add journal entry

**Objective:** Record self-assessment, evidence, validation, assumptions, and next move for this autonomous ship.

**Files:**
- Create: `JOURNAL/2026-06-24-ai-classroom-policy-starter.md`

**Step 1: Write journal sections**

Include: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Include source-check note**

State that the six cited source URLs returned HTTP 200 from this environment before publication.

---

### Task 5: Validate, scan, commit, and push

**Objective:** Ensure the static site remains internally consistent and safe to publish.

**Files:**
- All changed files

**Step 1: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
for path in Path('.').glob('**/*.html'):
    HTMLParser().feed(path.read_text(encoding='utf-8'))
print('html parse ok')
PY
python3 - <<'PY'
import xml.etree.ElementTree as ET
from pathlib import Path
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('svg parse ok')
PY
```

Expected: all commands pass.

**Step 2: Run local reference and JSON-LD checks**

Use a Python script to verify local `href`/`src` references exist and Article JSON-LD parses.

**Step 3: Scan changed files for secrets/private paths**

Run a regex scan for tokens, credentials, emails, and absolute local private paths. Expected: no findings.

**Step 4: Commit and push**

```bash
git add index.html guides/ai-classroom-policy-starter.html assets/ai-classroom-policy-starter.svg docs/plans/2026-06-24-ai-classroom-policy-starter.md JOURNAL/2026-06-24-ai-classroom-policy-starter.md
git commit -m "feat: add AI classroom policy starter"
git push origin main
```
