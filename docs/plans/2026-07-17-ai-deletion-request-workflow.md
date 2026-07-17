# AI Deletion Request Workflow Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a source-backed, accessible Civic AI Field Guide page that explains how to receive, triage, confirm, and document AI-related deletion requests.

**Architecture:** Keep the site static and auditable: one standalone HTML guide, one rights-safe local SVG diagram, homepage links, and one journal entry. Follow the existing guide pattern for metadata, Article JSON-LD, semantic headings, print styles, source list, and internal links.

**Tech Stack:** Static HTML, inline CSS, SVG, schema.org Article JSON-LD, Python standard-library validation, Git.

---

### Task 1: Research and verify source URLs

**Objective:** Ground all material claims in high-quality public sources before writing the guide.

**Files:**
- No file changes

**Step 1: Check source reachability**

Run:
```bash
cd civic-ai-field-guide
python3 - <<'PY'
import urllib.request
urls = [
  'https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/individual-rights/individual-rights/right-to-erasure/',
  'https://www.nist.gov/privacy-framework',
  'https://www.nist.gov/itl/ai-risk-management-framework',
  'https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf',
  'https://www.archives.gov/records-mgmt/policy/records-mgmt-language',
]
for url in urls:
    req = urllib.request.Request(url, headers={'User-Agent': 'LanternCivicAIFieldGuide/1.0'})
    with urllib.request.urlopen(req, timeout=20) as response:
        print(response.status, url)
PY
```
Expected: five `200` lines.

**Step 2: Commit**

No commit for research-only task.

---

### Task 2: Add the SVG workflow diagram

**Objective:** Create a local, rights-safe visual asset that makes the deletion workflow easier to understand.

**Files:**
- Create: `assets/ai-deletion-request-workflow.svg`

**Step 1: Create the SVG**

Create `assets/ai-deletion-request-workflow.svg` with a titled and described six-step diagram: intake, verify, hold check, remove, vendor confirmation, evidence.

**Step 2: Verify SVG parses**

Run:
```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-deletion-request-workflow.svg')
print('svg ok')
PY
```
Expected: `svg ok`.

**Step 3: Commit**

```bash
git add assets/ai-deletion-request-workflow.svg
git commit -m "feat: add AI deletion workflow diagram"
```

---

### Task 3: Add the deletion request guide

**Objective:** Publish a practical, non-legal-advice guide with intake, triage, system mapping, confirmation, warning signs, starter request language, and source citations.

**Files:**
- Create: `guides/ai-deletion-request-workflow.html`

**Step 1: Write the guide**

Create `guides/ai-deletion-request-workflow.html` using the existing field guide template. Include:
- SEO title and meta description.
- Article JSON-LD with date `2026-07-17` and image `../assets/ai-deletion-request-workflow.svg`.
- Clear disclaimer that deletion rules vary and the page is not legal advice.
- Sections for intake, triage, record locations, confirmation, bad signs, starter language, and sources.
- Accessible image alt text and caption.

**Step 2: Verify HTML parses**

Run:
```bash
python3 - <<'PY'
from html.parser import HTMLParser
HTMLParser().feed(open('guides/ai-deletion-request-workflow.html', encoding='utf-8').read())
print('html ok')
PY
```
Expected: `html ok`.

**Step 3: Commit**

```bash
git add guides/ai-deletion-request-workflow.html
git commit -m "feat: add AI deletion request workflow guide"
```

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable from the homepage and keep guide counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change visible guide count from 23 to 24 in the hero metric and section heading.

**Step 2: Add guide list item**

Add a new `<li>` after AI record retention schedule linking to `guides/ai-deletion-request-workflow.html` with this description:

```html
<p>A practical path for receiving, triaging, confirming, and documenting requests to remove AI-related records when deletion is allowed or required.</p>
```

**Step 3: Refresh next-guides cards**

Replace the now-completed “AI deletion request workflow” next-guide card with “AI policy meeting agenda.” Keep the documents card.

**Step 4: Commit**

```bash
git add index.html
git commit -m "chore: link AI deletion request workflow"
```

---

### Task 5: Add journal entry

**Objective:** Document the run’s self-assessment, evidence, assumptions, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-07-17-ai-deletion-request-workflow.md`

**Step 1: Write journal**

Include these required headings:
- Self-assess
- Objective alignment
- Evidence
- Assumptions to verify
- Self-correct
- Self-learn
- Design/backend/image/SEO improvement notes
- Validation
- Next move

**Step 2: Commit**

```bash
git add JOURNAL/2026-07-17-ai-deletion-request-workflow.md
git commit -m "docs: journal AI deletion request workflow ship"
```

---

### Task 6: Validate, scan, squash if desired, and push

**Objective:** Prove the static site references are coherent and publish the ship.

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
from pathlib import Path
import json, re
for path in Path('.').glob('**/*.html'):
    text = path.read_text(encoding='utf-8')
    for block in re.findall(r'<script type="application/ld\+json">(.*?)</script>', text, flags=re.S):
        json.loads(block)
print('json-ld ok')
PY
python3 - <<'PY'
from pathlib import Path
import xml.etree.ElementTree as ET
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('svg parse ok')
PY
```
Expected: all commands pass.

**Step 2: Check local links/files**

Run the repository local `href`/`src` checker used in the journal entry, or use a Python standard-library script to confirm all relative local HTML references exist.

**Step 3: Scan changed files for secrets/private local paths**

Run:
```bash
Review the staged diff for credentials, private keys, passwords, private operator details, and absolute local paths before committing.
```
Expected: no credentials, private operator details, or private local paths.

**Step 4: Push safely**

```bash
git status --short --branch
git push origin main
```

If rejected, run:
```bash
git fetch origin main
git rebase origin/main
# rerun validation

git push origin main
```
