# AI Staff Training Log Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed field guide page and visual asset that help teams track AI training status, scope, evidence, and refresh triggers.

**Architecture:** Keep the project static and dependency-free: one standalone HTML guide, one local SVG, homepage discovery updates, and one journal entry. Reuse the existing guide-page CSS pattern so the ship is maintainable and consistent with the privacy/governance cluster.

**Tech Stack:** Static HTML, inline CSS, schema.org Article JSON-LD, SVG, Python standard-library validation, Git/GitHub.

---

### Task 1: Research and verify source URLs

**Objective:** Ground the training-log guide in high-quality public sources without making unsupported claims.

**Files:**
- No file changes.

**Step 1: Check sources**

Run:

```bash
python3 - <<'PY'
import urllib.request
urls = [
  'https://www.nist.gov/itl/ai-risk-management-framework',
  'https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf',
  'https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf',
  'https://www.cisa.gov/resources-tools/resources/secure-by-design',
  'https://www.ftc.gov/business-guidance/resources/protecting-personal-information-guide-business',
  'https://www.w3.org/TR/WCAG22/',
  'https://www.ada.gov/resources/web-guidance/',
]
for url in urls:
    req = urllib.request.Request(url, headers={'User-Agent': 'LanternCivicAIFieldGuide/1.0'})
    with urllib.request.urlopen(req, timeout=20) as r:
        print(r.status, url)
PY
```

Expected: each URL returns `200`.

**Step 2: Commit**

No commit for research-only work.

---

### Task 2: Add AI staff training log guide

**Objective:** Create a practical, source-backed HTML guide with a starter table and scenario checks.

**Files:**
- Create: `guides/ai-staff-training-log.html`

**Step 1: Write the page**

Create a standalone HTML page that includes:

- Title: `AI Staff Training Log | Civic AI Field Guide`
- Meta description focused on tracking training for AI policy, privacy, security, accessibility, human review, and stop rules.
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-07-27`.
- A short answer warning that a training log is accountability evidence, not proof of safety or compliance.
- Sections for minimum fields, required topics, starter template, scenario checks, bad signs, starter language, related pages, and sources.
- Links to the new SVG at `../assets/ai-staff-training-log.svg`.
- Related internal links to document intake, data minimization, source checking, accessibility review, incident response, model update review, and system owner pages.

**Step 2: Verify the file exists**

Run: `test -f guides/ai-staff-training-log.html`
Expected: exit code 0.

**Step 3: Commit**

```bash
git add guides/ai-staff-training-log.html
git commit -m "feat: add AI staff training log guide"
```

---

### Task 3: Add local SVG visual

**Objective:** Add a rights-safe visual that improves comprehension of the training-log cycle.

**Files:**
- Create: `assets/ai-staff-training-log.svg`

**Step 1: Create SVG**

Create an SVG with:

- `<title id="title">AI staff training log cycle</title>`
- `<desc id="desc">A five-part flow for AI staff training: assign roles, teach rules, practice scenarios, record evidence, and refresh after changes.</desc>`
- Five labeled steps: Assign, Teach, Practice, Record, Refresh.
- A caption-compatible central message: not just “AI training complete.”

**Step 2: Verify XML parse**

Run:

```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-staff-training-log.svg')
print('SVG OK')
PY
```

Expected: `SVG OK`.

**Step 3: Commit**

```bash
git add assets/ai-staff-training-log.svg
git commit -m "feat: add AI staff training visual"
```

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable and keep homepage counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update count and list**

Change:

```html
<div class="metric"><b>27</b><span>starter guides</span></div>
<h2>Twenty-seven guides worth bookmarking.</h2>
```

to:

```html
<div class="metric"><b>28</b><span>starter guides</span></div>
<h2>Twenty-eight guides worth bookmarking.</h2>
```

Add after the AI document intake checklist:

```html
<li>
  <div>
    <h3><a href="guides/ai-staff-training-log.html">AI staff training log</a></h3>
    <p>A lightweight record for tracking who has been trained on AI policy, privacy, security, accessibility, human review, and stop rules.</p>
  </div>
</li>
```

Replace the next-topic card for `AI staff training log` with `AI communication review checklist`.

**Step 2: Verify count**

Run:

```bash
python3 - <<'PY'
from pathlib import Path
html = Path('index.html').read_text()
assert '<b>28</b><span>starter guides</span>' in html
assert 'Twenty-eight guides worth bookmarking.' in html
assert 'guides/ai-staff-training-log.html' in html
print('Homepage OK')
PY
```

Expected: `Homepage OK`.

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: list AI staff training log on homepage"
```

---

### Task 5: Add journal entry and validate

**Objective:** Document the self-assessment, validation, and next move before shipping.

**Files:**
- Create: `JOURNAL/2026-07-27-ai-staff-training-log.md`

**Step 1: Write journal**

Include sections:

- Self-assess
- Objective alignment
- Evidence
- Assumptions to verify
- Self-correct
- Self-learn
- Design/backend/image/SEO improvement notes
- Validation
- Next move

**Step 2: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
for path in Path('.').glob('**/*.html'):
    HTMLParser().feed(path.read_text(encoding='utf-8'))
print('HTML parse OK')
PY
python3 - <<'PY'
from pathlib import Path
from html.parser import HTMLParser
class LinkParser(HTMLParser):
    def __init__(self): super().__init__(); self.refs=[]
    def handle_starttag(self, tag, attrs):
        attrs=dict(attrs)
        for key in ('href','src'):
            if key in attrs: self.refs.append(attrs[key])
for path in Path('.').glob('**/*.html'):
    p=LinkParser(); p.feed(path.read_text(encoding='utf-8'))
    for ref in p.refs:
        if ref.startswith(('http://','https://','mailto:','tel:','#','bitcoin:','ethereum:','solana:')) or ref.startswith('data:'):
            continue
        target=(path.parent / ref.split('#')[0]).resolve()
        if ref.split('#')[0] and not target.exists():
            raise SystemExit(f'Missing local ref in {path}: {ref}')
print('Local refs OK')
PY
python3 - <<'PY'
import json, re
from pathlib import Path
for path in Path('.').glob('**/*.html'):
    text=path.read_text(encoding='utf-8')
    for block in re.findall(r'<script type="application/ld\+json">(.*?)</script>', text, re.S):
        json.loads(block)
print('JSON-LD OK')
PY
python3 - <<'PY'
import xml.etree.ElementTree as ET
from pathlib import Path
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('SVG parse OK')
PY
```

Expected: all commands pass.

**Step 3: Scan for secrets**

Run a changed-file scan for token-like strings and absolute private paths. Expected: no credentials, tokens, operator personal info, private logs, or local private paths in public content.

**Step 4: Commit and push**

```bash
git add index.html guides/ai-staff-training-log.html assets/ai-staff-training-log.svg docs/plans/2026-07-27-ai-staff-training-log.md JOURNAL/2026-07-27-ai-staff-training-log.md
git commit -m "feat: add AI staff training log"
git push origin main
```
