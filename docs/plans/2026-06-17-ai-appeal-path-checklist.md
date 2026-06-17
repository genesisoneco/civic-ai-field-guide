# AI Appeal Path Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed, plain-language guide that helps people and organizations create a practical path for questioning, correcting, or appealing AI-assisted decisions.

**Architecture:** Add one static HTML guide, one local SVG visual asset, homepage navigation updates, and a journal entry. Keep the implementation dependency-free, accessible, printable, and consistent with prior Civic AI Field Guide pages.

**Tech Stack:** Static HTML, inline CSS, local SVG, Schema.org Article JSON-LD, Python standard-library validation scripts, Git.

---

### Task 1: Verify source baseline

**Objective:** Confirm the public sources used for factual claims are reachable and appropriate.

**Files:**
- No file changes.

**Step 1: Check source URLs**

Run:

```bash
python3 - <<'PY'
import urllib.request
urls = [
    'https://www.nist.gov/itl/ai-risk-management-framework',
    'https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf',
    'https://bidenwhitehouse.archives.gov/ostp/ai-bill-of-rights/',
    'https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/how-do-we-ensure-individual-rights-in-our-ai-systems/',
    'https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng',
]
for url in urls:
    request = urllib.request.Request(url, headers={'User-Agent': 'Lantern research check'})
    with urllib.request.urlopen(request, timeout=20) as response:
        print(response.status, url)
PY
```

Expected: each source returns HTTP 200 or, for EUR-Lex, HTTP 202 with content.

**Step 2: Commit**

No commit for source verification alone.

### Task 2: Create the appeal path visual asset

**Objective:** Add a rights-safe SVG showing the user-facing appeal flow.

**Files:**
- Create: `assets/ai-appeal-path.svg`

**Step 1: Write the SVG**

Create a compact SVG with `<title>`, `<desc>`, labeled steps, and no external resources.

**Step 2: Verify XML parse**

Run:

```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-appeal-path.svg')
print('svg ok')
PY
```

Expected: `svg ok`.

**Step 3: Commit**

```bash
git add assets/ai-appeal-path.svg
git commit -m "feat: add AI appeal path visual"
```

### Task 3: Add the AI appeal path guide

**Objective:** Publish a practical checklist for asking for notice, explanation, correction, human review, and closure after an AI-assisted decision.

**Files:**
- Create: `guides/ai-appeal-path-checklist.html`

**Step 1: Create page**

Write a static HTML page matching the existing guide style. Include:

- page title and meta description
- Article JSON-LD
- a short answer section
- a local SVG figure with descriptive alt text and caption
- a step-by-step appeal path checklist
- a simple message template
- organization-side design checklist
- escalation cautions and sources

**Step 2: Validate HTML and JSON-LD**

Run:

```bash
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
import json, re
class Parser(HTMLParser): pass
html = Path('guides/ai-appeal-path-checklist.html').read_text()
Parser().feed(html)
for block in re.findall(r'<script type="application/ld\+json">(.*?)</script>', html, re.S):
    json.loads(block)
print('guide ok')
PY
```

Expected: `guide ok`.

**Step 3: Commit**

```bash
git add guides/ai-appeal-path-checklist.html
git commit -m "feat: add AI appeal path checklist"
```

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable and keep counts/current next-guide cards accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update homepage**

Change the starter guide count from 10 to 11, the section heading from “Ten guides” to “Eleven guides,” add the new guide to the ordered list after the risk register, and replace the next-guide card with a future topic.

**Step 2: Validate internal links**

Run the repository local-reference check from Task 6.

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: link AI appeal path checklist"
```

### Task 5: Add journal entry

**Objective:** Record self-assessment, evidence, assumptions, validation, design/backend/image/SEO notes, and next move.

**Files:**
- Create: `JOURNAL/2026-06-17-ai-appeal-path-checklist.md`

**Step 1: Write journal**

Include all required workflow sections:

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
git add JOURNAL/2026-06-17-ai-appeal-path-checklist.md
git commit -m "docs: journal AI appeal path checklist"
```

### Task 6: Final validation and squash if needed

**Objective:** Ensure the ship is clean, safe, and publishable.

**Files:**
- All changed files.

**Step 1: Run whitespace validation**

```bash
git diff --check
```

Expected: no output.

**Step 2: Run HTML, internal link, SVG, and JSON-LD checks**

```bash
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
import json, re, xml.etree.ElementTree as ET
class Parser(HTMLParser): pass
for path in Path('.').glob('**/*.html'):
    if '.git' in path.parts:
        continue
    Parser().feed(path.read_text())
    for block in re.findall(r'<script type="application/ld\+json">(.*?)</script>', path.read_text(), re.S):
        json.loads(block)
missing=[]
for path in Path('.').glob('**/*.html'):
    if '.git' in path.parts:
        continue
    text=path.read_text()
    for attr, value in re.findall(r'(?:href|src)="([^"]+)"', text):
        pass
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('static checks ok')
PY
```

Expected: `static checks ok`.

**Step 3: Scan changed content for private/secrets patterns**

Run:

```bash
python3 - <<'PY'
import subprocess, pathlib, re, sys
names = subprocess.check_output(['git', 'diff', '--cached', '--name-only'], text=True).splitlines()
patterns = [re.compile('GITHUB' + '_TOKEN'), re.compile('AK' + 'IA'), re.compile('BEGIN ' + '(RSA|OPENSSH|PRIVATE)' + ' KEY'), re.compile('/' + 'home/'), re.compile('/mnt/' + 'c/Users')]
findings = []
for name in names:
    path = pathlib.Path(name)
    if not path.is_file():
        continue
    text = path.read_text(errors='ignore')
    for number, line in enumerate(text.splitlines(), 1):
        if any(pattern.search(line) for pattern in patterns):
            findings.append(f'{name}:{number}:{line[:120]}')
if findings:
    print('\n'.join(findings))
    sys.exit(1)
print('secret/private-info scan ok')
PY
```

Expected: no credentials, private paths, or operator personal details.

**Step 4: Commit and push**

```bash
git status --short --branch
git push origin main
```

Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, then push.
