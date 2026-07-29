# AI Communication Review Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed field guide page and visual asset that help teams review AI-assisted public communications before publication.

**Architecture:** Keep the project static and dependency-free: one standalone HTML guide, one local SVG review flow, homepage discovery updates, and one journal entry. Reuse the existing guide-page CSS pattern so the ship is consistent with the governance/privacy/accessibility cluster.

**Tech Stack:** Static HTML, inline CSS, schema.org Article JSON-LD, SVG, Python standard-library validation, Git/GitHub.

---

### Task 1: Research and verify source URLs

**Objective:** Ground the communication-review guide in high-quality public sources without making unsupported claims.

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
  'https://www.plainlanguage.gov/guidelines/',
  'https://www.w3.org/TR/WCAG22/',
  'https://www.ada.gov/resources/web-guidance/',
  'https://www.lep.gov/language-access-planning',
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

### Task 2: Add AI communication review checklist guide

**Objective:** Create a practical, source-backed HTML guide with a pre-publication checklist, stop rules, starter log, and reusable review language.

**Files:**
- Create: `guides/ai-communication-review-checklist.html`

**Step 1: Write the page**

Create a standalone HTML page that includes:

- Title: `AI Communication Review Checklist | Civic AI Field Guide`
- Meta description focused on checking AI-assisted public notices, emails, web pages, translations, captions, and statements before publication.
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-07-29`.
- A short answer explaining that AI can help draft communications but cannot replace review for facts, rights, access, tone, privacy, and accountability.
- Sections for review flow, minimum checks, high-risk messages, starter sign-off log, stop rules, related pages, and sources.
- Link to `../assets/ai-communication-review-checklist.svg` with descriptive alt text.

**Step 2: Verify the file exists**

Run: `test -f guides/ai-communication-review-checklist.html`
Expected: exit code 0.

**Step 3: Commit**

```bash
git add guides/ai-communication-review-checklist.html
git commit -m "feat: add AI communication review checklist"
```

---

### Task 3: Add local SVG visual

**Objective:** Add a rights-safe visual that improves comprehension of the pre-publication review loop.

**Files:**
- Create: `assets/ai-communication-review-checklist.svg`

**Step 1: Create SVG**

Create an SVG with:

- `<title id="title">AI communication review flow</title>`
- `<desc id="desc">A six-part flow for reviewing AI-assisted communications: purpose, facts, people, access, privacy, and publish or pause.</desc>`
- Six labeled review gates: Purpose, Facts, People, Access, Privacy, Publish/Pause.
- A central reminder: `Public copy needs accountable review.`

**Step 2: Verify XML parse**

Run:

```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-communication-review-checklist.svg')
print('SVG OK')
PY
```

Expected: `SVG OK`.

**Step 3: Commit**

```bash
git add assets/ai-communication-review-checklist.svg
git commit -m "feat: add AI communication review visual"
```

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable and keep homepage counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update count and list**

Change:

```html
<div class="metric"><b>28</b><span>starter guides</span></div>
<h2>Twenty-eight guides worth bookmarking.</h2>
```

to:

```html
<div class="metric"><b>29</b><span>starter guides</span></div>
<h2>Twenty-nine guides worth bookmarking.</h2>
```

Add after the AI staff training log:

```html
<li>
  <div>
    <h3><a href="guides/ai-communication-review-checklist.html">AI communication review checklist</a></h3>
    <p>A pre-publication checklist for AI-assisted notices, emails, web pages, translations, captions, and public statements.</p>
  </div>
</li>
```

Replace the next-topic card for `AI communication review checklist` with `AI policy meeting agenda` or another future topic that is not already shipped.

**Step 2: Verify count**

Run:

```bash
python3 - <<'PY'
from pathlib import Path
html = Path('index.html').read_text()
assert '<b>29</b><span>starter guides</span>' in html
assert 'Twenty-nine guides worth bookmarking.' in html
assert 'guides/ai-communication-review-checklist.html' in html
print('Homepage OK')
PY
```

Expected: `Homepage OK`.

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: list AI communication review checklist"
```

---

### Task 5: Add journal entry and validate

**Objective:** Document the self-assessment, validation, and next move before shipping.

**Files:**
- Create: `JOURNAL/2026-07-29-ai-communication-review-checklist.md`

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
from urllib.parse import urlparse
missing=[]
for path in Path('.').glob('**/*.html'):
    text=path.read_text(encoding='utf-8')
    import re
    for attr, value in re.findall(r'(href|src)="([^"]+)"', text):
        if value.startswith(('#','mailto:','tel:','bitcoin:','ethereum:','solana:')):
            continue
        if urlparse(value).scheme in {'http','https'}:
            continue
        target=(path.parent/value).resolve()
        if not target.exists():
            missing.append(f'{path}: {attr}={value}')
if missing:
    raise SystemExit('\n'.join(missing))
print('Internal links OK')
PY
python3 - <<'PY'
import xml.etree.ElementTree as ET
from pathlib import Path
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('SVG parse OK')
PY
python3 - <<'PY'
import json,re
from pathlib import Path
for path in Path('.').glob('**/*.html'):
    for block in re.findall(r'<script type="application/ld\+json">(.*?)</script>', path.read_text(encoding='utf-8'), re.S):
        json.loads(block)
print('JSON-LD OK')
PY
```

Expected: all checks pass.

**Step 3: Scan changed files for secrets/private paths**

Run:

```bash
git diff --cached --name-only | xargs grep -nE '(/home/sejcore|BEGIN [A-Z ]*PRIVATE KEY|GITHUB_TOKEN|ghp_|password|secret|credential)' || true
```

Expected: no actual secrets, credentials, operator personal details, private logs, or absolute local private paths in public copy.

**Step 4: Commit and push**

```bash
git add docs/plans/2026-07-29-ai-communication-review-checklist.md guides/ai-communication-review-checklist.html assets/ai-communication-review-checklist.svg index.html JOURNAL/2026-07-29-ai-communication-review-checklist.md
git commit -m "feat: add AI communication review checklist"
git push origin main
```

Expected: push succeeds. If rejected, fetch/rebase once, re-run validation, then push.
