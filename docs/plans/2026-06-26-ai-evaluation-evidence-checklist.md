# AI Evaluation Evidence Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed guide that helps readers ask what evidence should exist before relying on an AI system.

**Architecture:** Keep the site static and consistent with existing single-page guide patterns. Add one HTML guide, one local SVG visual asset, homepage links/count updates, and a journal entry documenting validation and assumptions.

**Tech Stack:** Static HTML, inline CSS, SVG, Python standard library validation, Git.

---

### Task 1: Add the evidence checklist guide page

**Objective:** Create a plain-language, cited guide for evaluating AI evidence before adoption or reliance.

**Files:**
- Create: `guides/ai-evaluation-evidence-checklist.html`

**Step 1: Write the page**

Create a complete static HTML file following existing guide styles. Include:
- SEO title and meta description.
- Article JSON-LD.
- Short answer card.
- Figure referencing `../assets/ai-evaluation-evidence-checklist.svg`.
- Use cases, evidence checklist, minimum evidence bundle, meeting script, warning signs, and source list.

**Step 2: Verify sources are reachable**

Run:

```bash
python3 - <<'PY'
import urllib.request
urls = [
  'https://www.nist.gov/itl/ai-risk-management-framework',
  'https://www.nist.gov/itl/ai-risk-management-framework/ai-rmf-playbook',
  'https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10',
  'https://oecd.ai/en/ai-principles',
  'https://www.w3.org/WAI/test-evaluate/',
  'https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai',
  'https://www.gov.uk/government/collections/algorithmic-transparency-recording-standard-hub'
]
for url in urls:
    req = urllib.request.Request(url, method='HEAD', headers={'User-Agent':'Lantern source check'})
    try:
        with urllib.request.urlopen(req, timeout=20) as r:
            print(r.status, url)
    except Exception:
        req = urllib.request.Request(url, headers={'User-Agent':'Lantern source check'})
        with urllib.request.urlopen(req, timeout=20) as r:
            print(r.status, url)
PY
```

Expected: HTTP 200 for each source.

**Step 3: Commit checkpoint after validation later**

Do not commit until all related files and validation are complete.

### Task 2: Add the local SVG evidence visual

**Objective:** Add a rights-safe, lightweight diagram that improves comprehension of evidence flow.

**Files:**
- Create: `assets/ai-evaluation-evidence-checklist.svg`

**Step 1: Create SVG**

Add a local SVG with `<title>` and `<desc>` showing the sequence: purpose → test cases → results → failures → monitoring → decision.

**Step 2: Verify SVG parses**

Run XML validation across SVG files.

Expected: PASS.

### Task 3: Update homepage information architecture

**Objective:** Make the new guide discoverable from the homepage and refresh the “next guides” cards.

**Files:**
- Modify: `index.html`

**Step 1: Update count**

Change starter guide count from 14 to 15 in both the metric card and section heading.

**Step 2: Add guide list item**

Append `guides/ai-evaluation-evidence-checklist.html` with a short, descriptive summary.

**Step 3: Refresh next guide cards**

Replace the now-built next card with a new future guide topic.

### Task 4: Add the journal entry

**Objective:** Document self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-06-26-ai-evaluation-evidence-checklist.md`

**Step 1: Write journal sections**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

### Task 5: Validate, scan, commit, and push

**Objective:** Ensure the ship is safe, correct, and public.

**Files:**
- All changed files.

**Step 1: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
import json, re, xml.etree.ElementTree as ET
class P(HTMLParser): pass
for p in Path('.').glob('**/*.html'):
    P().feed(p.read_text(encoding='utf-8'))
for p in Path('assets').glob('*.svg'):
    ET.parse(p)
print('parse checks passed')
PY
```

**Step 2: Run local link/file checks and secret scan**

Use a Python script to ensure local `href`/`src` references exist and changed files do not include tokens, credentials, operator personal info, or absolute private paths.

**Step 3: Commit**

```bash
git add index.html guides/ai-evaluation-evidence-checklist.html assets/ai-evaluation-evidence-checklist.svg docs/plans/2026-06-26-ai-evaluation-evidence-checklist.md JOURNAL/2026-06-26-ai-evaluation-evidence-checklist.md
git commit -m "feat: add AI evaluation evidence checklist"
```

**Step 4: Push**

```bash
git push origin main
```

If rejected, fetch/rebase once, rerun validation, then push again.
