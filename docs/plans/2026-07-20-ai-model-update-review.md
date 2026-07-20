# AI Model Update Review Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a source-backed, accessible Civic AI Field Guide page that helps teams review AI model changes, vendor feature rollouts, and policy updates before they quietly alter risk.

**Architecture:** Keep the site static and auditable: one standalone HTML guide, one rights-safe local SVG diagram, homepage links/count updates, and one journal entry. Reuse the existing guide pattern for metadata, Article JSON-LD, semantic headings, print styles, source list, and internal discovery.

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
  'https://www.nist.gov/itl/ai-risk-management-framework',
  'https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf',
  'https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf',
  'https://owasp.org/www-project-top-10-for-large-language-model-applications/',
  'https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/',
  'https://www.cisa.gov/resources-tools/resources/secure-by-design',
]
for url in urls:
    req = urllib.request.Request(url, headers={'User-Agent': 'LanternCivicAIFieldGuide/1.0'})
    with urllib.request.urlopen(req, timeout=25) as response:
        print(response.status, url)
PY
```
Expected: six `200` lines.

**Step 2: Commit**

No commit for research-only task.

---

### Task 2: Add the SVG update review diagram

**Objective:** Create a local, rights-safe visual asset that makes the update review loop easy to understand.

**Files:**
- Create: `assets/ai-model-update-review.svg`

**Step 1: Create the SVG**

Create `assets/ai-model-update-review.svg` with a titled and described six-step diagram: notice, compare, test, update controls, communicate, monitor.

**Step 2: Verify SVG parses**

Run:
```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-model-update-review.svg')
print('svg ok')
PY
```
Expected: `svg ok`.

**Step 3: Commit**

```bash
git add assets/ai-model-update-review.svg
git commit -m "feat: add AI model update review diagram"
```

---

### Task 3: Add the model update review guide

**Objective:** Publish a practical, source-backed checklist for reviewing vendor model changes, feature rollouts, policy changes, prompt/template changes, and retention/logging changes.

**Files:**
- Create: `guides/ai-model-update-review.html`

**Step 1: Write the guide**

Create `guides/ai-model-update-review.html` using the existing field guide template. Include:
- SEO title and meta description.
- Article JSON-LD with date `2026-07-20` and image `../assets/ai-model-update-review.svg`.
- Short answer explaining that a model update review is a change-control checkpoint, not a full audit.
- Sections for review triggers, before/after comparison, local regression tests, controls/notices/training, monitoring after rollout, bad signs, starter review language, and sources.
- Internal links to existing guides on vendor disclosure, evaluation evidence, incident response, public notice, data minimization, retention, and deletion requests.
- Accessible image alt text and caption.

**Step 2: Verify HTML parses**

Run:
```bash
python3 - <<'PY'
from html.parser import HTMLParser
HTMLParser().feed(open('guides/ai-model-update-review.html', encoding='utf-8').read())
print('html ok')
PY
```
Expected: `html ok`.

**Step 3: Commit**

```bash
git add guides/ai-model-update-review.html
git commit -m "feat: add AI model update review guide"
```

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable from the homepage and keep guide counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change visible guide count from 24 to 25 in the hero metric and section heading.

**Step 2: Add guide list item**

Add a new `<li>` after AI deletion request workflow linking to `guides/ai-model-update-review.html` with this description:

```html
<p>A lightweight review checklist for checking whether a vendor model change, feature rollout, or policy update affects risk, notices, testing, retention, deletion, training, or monitoring.</p>
```

**Step 3: Refresh next-guides cards**

Replace the now-completed “AI model update review” next-guide card with “AI policy exception log.” Keep the policy meeting agenda and documents cards.

**Step 4: Commit**

```bash
git add index.html
git commit -m "chore: link AI model update review"
```

---

### Task 5: Add journal entry

**Objective:** Document the run’s self-assessment, evidence, assumptions, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-07-20-ai-model-update-review.md`

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
git add JOURNAL/2026-07-20-ai-model-update-review.md
git commit -m "docs: journal AI model update review ship"
```

---

### Task 6: Validate, scan, and push

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
    for block in re.findall(r'<script type="application/ld\\+json">(.*?)</script>', text, flags=re.S):
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

Run a Python standard-library script that confirms all relative local `href` and `src` references in HTML files resolve to tracked local files or in-page anchors.

**Step 3: Scan changed files for secrets/private local paths**

Run:
```bash
python3 - <<'PY'
import re, subprocess
patterns = [
    r'GITHUB_TOKEN', r'BEGIN (RSA|OPENSSH|PRIVATE) KEY', r'password', r'secret',
    r'token=', r'ghp_', r'github_pat_', r'/home/[A-Za-z0-9._-]+', r'/mnt/[a-z]/Users/[^\s<>"\']+',
]
files = subprocess.check_output(['git', 'diff', '--cached', '--name-only'], text=True).splitlines()
for path in files:
    try:
        text = open(path, encoding='utf-8').read()
    except UnicodeDecodeError:
        continue
    for i, line in enumerate(text.splitlines(), 1):
        if any(re.search(pattern, line, re.I) for pattern in patterns):
            print(f'{path}:{i}: possible private content')
PY
```
Expected: no matches, except public donation addresses if support files were changed.

**Step 4: Commit and push**

```bash
git add docs/plans/2026-07-20-ai-model-update-review.md assets/ai-model-update-review.svg guides/ai-model-update-review.html index.html JOURNAL/2026-07-20-ai-model-update-review.md
git commit -m "feat: add AI model update review"
git push origin main
```

If push is rejected, run:
```bash
git fetch origin main
git rebase origin/main
# rerun validation commands
git push origin main
```
If rebase or validation fails, stop and report the full error.
