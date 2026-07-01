# AI Translation and Language Access Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed public guide that helps schools, workplaces, civic offices, and community groups use AI translation cautiously while protecting language access, privacy, accessibility, and human review.

**Architecture:** Keep the site static and auditable: one standalone HTML guide, one rights-safe local SVG diagram, homepage internal links, and a journal entry. Use the same lightweight pattern as recent guides so there is no framework or backend expansion.

**Tech Stack:** Static HTML, inline CSS, local SVG, Schema.org Article JSON-LD, Git, Python standard library validation.

---

### Task 1: Confirm source base and write the implementation plan

**Objective:** Record the intended update and source set before publishing public claims.

**Files:**
- Create: `docs/plans/2026-07-01-ai-translation-language-access.md`

**Step 1: Verify source reachability**

Run:
```bash
python3 - <<'PY'
import urllib.request
urls = [
  'https://www.lep.gov/sites/lep/files/resources/MTReport.pdf',
  'https://www.justice.gov/crt/fcs/TitleVI-Overview',
  'https://www.nist.gov/itl/ai-risk-management-framework',
  'https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10',
  'https://unesdoc.unesco.org/ark:/48223/pf0000386693',
  'https://www.w3.org/WAI/fundamentals/accessibility-intro/'
]
for url in urls:
    request = urllib.request.Request(url, method='HEAD', headers={'User-Agent': 'Lantern link check'})
    with urllib.request.urlopen(request, timeout=20) as response:
        print(response.status, url)
PY
```
Expected: all listed sources return `200`.

**Step 2: Commit**

```bash
git add docs/plans/2026-07-01-ai-translation-language-access.md
git commit -m "docs: plan AI translation language access guide"
```

### Task 2: Add a rights-safe translation workflow SVG

**Objective:** Create an accessible local diagram that explains the safe review loop without external image rights risk.

**Files:**
- Create: `assets/ai-translation-language-access.svg`

**Step 1: Add the SVG**

Create an SVG with:
- `<title>`: “AI translation language access review loop”
- `<desc>`: “A five-step loop showing scope, privacy check, AI draft, human review, and feedback.”
- Five labeled nodes: Scope need, Protect privacy, Draft carefully, Human review, Feedback loop.

**Step 2: Validate XML**

Run:
```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-translation-language-access.svg')
print('svg ok')
PY
```
Expected: `svg ok`.

**Step 3: Commit**

```bash
git add assets/ai-translation-language-access.svg
git commit -m "design: add AI translation review diagram"
```

### Task 3: Add the AI translation and language access guide

**Objective:** Publish a practical, cited HTML guide with checklists, review rules, and source links.

**Files:**
- Create: `guides/ai-translation-language-access.html`

**Step 1: Write the page**

Include:
- Descriptive title and meta description.
- Article JSON-LD with date `2026-07-01` and SVG image path.
- Short answer: AI translation can expand access, but should not silently replace qualified human language support where stakes, rights, health, money, safety, legal status, or education outcomes are involved.
- Safety sections: when AI translation is reasonable, when human review is needed, privacy checks, accessibility checks, a plain-language disclosure template, and a source list.
- Public claim discipline: source claims to LEP.gov machine translation report, DOJ Title VI overview, NIST AI RMF, UNESCO generative AI education guidance, and W3C accessibility introduction.

**Step 2: Parse HTML**

Run:
```bash
python3 - <<'PY'
from html.parser import HTMLParser
HTMLParser().feed(open('guides/ai-translation-language-access.html', encoding='utf-8').read())
print('html ok')
PY
```
Expected: `html ok`.

**Step 3: Commit**

```bash
git add guides/ai-translation-language-access.html
git commit -m "feat: add AI translation language access guide"
```

### Task 4: Update homepage discovery links

**Objective:** Make the new guide discoverable and keep homepage counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update count and list**

Change:
- `16` starter guides → `17` starter guides.
- “Sixteen guides worth bookmarking.” → “Seventeen guides worth bookmarking.”
- Add a guide list item linking to `guides/ai-translation-language-access.html`.
- Replace the next-topic card for AI translation with another future topic.

**Step 2: Check local links**

Run the project link checker from Task 6.
Expected: no missing local links.

**Step 3: Commit**

```bash
git add index.html
git commit -m "seo: link AI translation language access guide"
```

### Task 5: Add the run journal

**Objective:** Document self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-07-01-ai-translation-language-access.md`

**Step 1: Write journal sections**

Include these headings:
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
git add JOURNAL/2026-07-01-ai-translation-language-access.md
git commit -m "docs: journal AI translation language access ship"
```

### Task 6: Validate, scan, squash if desired, and push

**Objective:** Prove the static site changed safely and publish the ship.

**Files:**
- Inspect all changed files.

**Step 1: Run validation**

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
import re, urllib.parse
missing=[]
for html in Path('.').glob('**/*.html'):
    text=html.read_text(encoding='utf-8')
    for attr in ('href','src'):
        for m in re.finditer(attr + r'="([^"]+)"', text):
            url=m.group(1)
            if url.startswith(('#','http:','https:','mailto:','tel:','bitcoin:','ethereum:','solana:')): continue
            target=(html.parent / urllib.parse.urlsplit(url).path).resolve()
            if not target.exists(): missing.append((str(html), url))
if missing: raise SystemExit('\n'.join(map(str, missing)))
print('local links ok')
PY
python3 - <<'PY'
from pathlib import Path
import xml.etree.ElementTree as ET
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('svg parse ok')
PY
python3 - <<'PY'
from html.parser import HTMLParser
import json
from pathlib import Path
class P(HTMLParser):
    def __init__(self): super().__init__(); self.in_ld=False; self.buf=[]; self.blocks=[]
    def handle_starttag(self, tag, attrs):
        if tag == 'script' and dict(attrs).get('type') == 'application/ld+json': self.in_ld=True; self.buf=[]
    def handle_data(self, data):
        if self.in_ld: self.buf.append(data)
    def handle_endtag(self, tag):
        if tag == 'script' and self.in_ld:
            self.blocks.append(''.join(self.buf)); self.in_ld=False
count=0
for path in Path('.').glob('**/*.html'):
    p=P(); p.feed(path.read_text(encoding='utf-8'))
    for block in p.blocks: json.loads(block); count+=1
print(f'json-ld parse ok: {count}')
PY
```
Expected: all checks pass.

**Step 2: Secret/private-path scan**

Run:
```bash
git diff --cached --name-only | xargs grep -nE '(GITHUB_TOKEN|BEGIN .*PRIVATE KEY|/[A-Za-z0-9._-]+/[A-Za-z0-9._-]+/projects|/mnt/[a-z]/Users|password|secret|token)' || true
```
Expected: no credentials or local private paths; ordinary public words like “privacy” are acceptable only after manual review.

**Step 3: Push**

```bash
git status --short --branch
git push origin main
```
Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, then push.
