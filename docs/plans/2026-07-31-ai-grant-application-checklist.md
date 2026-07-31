# AI Grant Application Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed public guide that helps civic teams review AI-assisted grant applications before submission.

**Architecture:** Keep the site static and lightweight: one standalone HTML guide, one local SVG visual, one homepage discovery update, and one journal entry. Reuse the existing guide pattern so the page works without a build system and remains inspectable in GitHub Pages.

**Tech Stack:** Static HTML, inline CSS, SVG, JSON-LD, Python standard-library validation, git.

---

### Task 1: Verify source material and page scope

**Objective:** Confirm the guide can make narrow, source-backed claims without overstating grant-law requirements.

**Files:**
- Create: `docs/plans/2026-07-31-ai-grant-application-checklist.md`
- Create: `guides/ai-grant-application-checklist.html`
- Create: `assets/ai-grant-application-checklist.svg`
- Modify: `index.html`
- Create: `JOURNAL/2026-07-31-ai-grant-application-checklist.md`

**Step 1: Check source URLs**

Run:

```bash
python3 - <<'PY'
import urllib.request
urls = [
    'https://www.ecfr.gov/current/title-2/subtitle-A/chapter-II/part-200',
    'https://www.grants.gov/applicants/workspace-overview',
    'https://www.justice.gov/civil/false-claims-act',
    'https://www.nist.gov/itl/ai-risk-management-framework',
    'https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf',
    'https://www.plainlanguage.gov/guidelines/',
]
for url in urls:
    req = urllib.request.Request(url, headers={'User-Agent': 'Lantern source check'})
    with urllib.request.urlopen(req, timeout=20) as response:
        print(response.status, url)
PY
```

Expected: every URL returns `200`.

**Step 2: Commit**

```bash
git add docs/plans/2026-07-31-ai-grant-application-checklist.md
git commit -m "docs: plan AI grant application checklist"
```

### Task 2: Add the grant review SVG

**Objective:** Add a rights-safe local visual that explains the review gates for an AI-assisted grant draft.

**Files:**
- Create: `assets/ai-grant-application-checklist.svg`

**Step 1: Create SVG**

Create an SVG with `<title>` and `<desc>` naming these gates: funder fit, evidence, budget, promises, compliance, and submit or revise.

**Step 2: Verify SVG parses**

Run:

```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-grant-application-checklist.svg')
print('svg ok')
PY
```

Expected: `svg ok`.

**Step 3: Commit**

```bash
git add assets/ai-grant-application-checklist.svg
git commit -m "design: add AI grant review visual"
```

### Task 3: Add the public guide page

**Objective:** Publish a practical, cited checklist for grant teams using AI as a drafting aid.

**Files:**
- Create: `guides/ai-grant-application-checklist.html`

**Step 1: Write guide HTML**

Include: title, meta description, Article JSON-LD, clear identity-safe public copy, short answer, SVG figure with alt text and caption, why it matters, minimum checks, risky grant sections, review workflow, sign-off log, stop rules, starter language, related pages, and sources.

**Step 2: Verify HTML parses**

Run:

```bash
python3 - <<'PY'
from html.parser import HTMLParser
HTMLParser().feed(open('guides/ai-grant-application-checklist.html', encoding='utf-8').read())
print('html ok')
PY
```

Expected: `html ok`.

**Step 3: Commit**

```bash
git add guides/ai-grant-application-checklist.html
git commit -m "feat: add AI grant application checklist"
```

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable and keep homepage counts/current-next-topic cards accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update count and list**

Change `29` to `30`, change “Twenty-nine” to “Thirty”, add a new guide list item for `guides/ai-grant-application-checklist.html`, and replace the next-topic card with another useful future topic.

**Step 2: Verify local links**

Run the repository local-link checker from Task 5.

Expected: all internal references resolve.

**Step 3: Commit**

```bash
git add index.html
git commit -m "seo: surface AI grant checklist on homepage"
```

### Task 5: Add journal and run final validation

**Objective:** Record the autonomous self-assessment and verify the ship before push.

**Files:**
- Create: `JOURNAL/2026-07-31-ai-grant-application-checklist.md`

**Step 1: Write journal entry**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

**Step 2: Run validation**

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
import json, re, xml.etree.ElementTree as ET
for path in Path('.').rglob('*.html'):
    HTMLParser().feed(path.read_text(encoding='utf-8'))
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
for path in Path('.').rglob('*.html'):
    text = path.read_text(encoding='utf-8')
    for match in re.finditer(r'<script type="application/ld\+json">(.*?)</script>', text, re.S):
        json.loads(match.group(1))
print('parse checks ok')
PY
python3 - <<'PY'
from pathlib import Path
from html.parser import HTMLParser
class LinkParser(HTMLParser):
    def __init__(self):
        super().__init__(); self.refs=[]
    def handle_starttag(self, tag, attrs):
        attrs=dict(attrs)
        for key in ('href','src'):
            if key in attrs:
                self.refs.append(attrs[key])
for html in Path('.').rglob('*.html'):
    p=LinkParser(); p.feed(html.read_text(encoding='utf-8'))
    for ref in p.refs:
        if ref.startswith(('#','http:','https:','mailto:','bitcoin:','ethereum:','solana:','javascript:')):
            continue
        target = (html.parent / ref.split('#',1)[0]).resolve()
        if ref.split('#',1)[0] and not target.exists():
            raise SystemExit(f'missing {ref} from {html}')
print('local links ok')
PY
```

Expected: all commands pass.

**Step 3: Scan changed files for secrets**

```bash
git diff --cached -- guides/ai-grant-application-checklist.html assets/ai-grant-application-checklist.svg index.html JOURNAL/2026-07-31-ai-grant-application-checklist.md docs/plans/2026-07-31-ai-grant-application-checklist.md | grep -Ei 'token|secret|password|/home/|/mnt/|credential|api[_-]?key' && exit 1 || true
```

Expected: no sensitive match.

**Step 4: Commit and push**

```bash
git add guides/ai-grant-application-checklist.html assets/ai-grant-application-checklist.svg index.html JOURNAL/2026-07-31-ai-grant-application-checklist.md docs/plans/2026-07-31-ai-grant-application-checklist.md
git commit -m "feat: add AI grant application checklist"
git push origin main
```
