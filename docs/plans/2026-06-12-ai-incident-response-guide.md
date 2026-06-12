# AI Incident Response Guide Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed guide that helps teams pause, disclose, repair, and learn when an AI-assisted mistake has already reached a user, record, publication, or decision.

**Architecture:** Add one static HTML guide, one local SVG visual asset, one homepage internal link, and one journal entry. Keep the page self-contained like existing guides, with semantic headings, source links, Article JSON-LD, and no backend dependency.

**Tech Stack:** Static HTML, inline CSS, SVG, Python standard-library validation, Git/GitHub.

---

### Task 1: Add the incident response guide page

**Objective:** Create a plain-language public guide for responding to AI-assisted mistakes.

**Files:**
- Create: `guides/ai-incident-response.html`

**Step 1: Write the page**

Create a complete HTML document with:
- title: `AI Incident Response Guide | Civic AI Field Guide`
- meta description focused on pause, disclosure, repair, and learning
- Article JSON-LD
- source-backed discussion of risk management using NIST AI RMF, NIST AI 600-1, and OMB M-24-10
- practical checklist sections: triage, evidence preservation, human review, user notice, repair, learning

**Step 2: Verify source links**

Run:

```bash
python3 - <<'PY'
import urllib.request
for url in [
 'https://www.nist.gov/itl/ai-risk-management-framework',
 'https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf',
 'https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf',
]:
    req = urllib.request.Request(url, headers={'User-Agent': 'Lantern link check'})
    with urllib.request.urlopen(req, timeout=20) as r:
        print(r.status, url)
PY
```

Expected: `200` for each URL.

**Step 3: Commit later with the rest of the ship**

Do not commit until the visual, homepage, journal, and validation tasks are complete.

---

### Task 2: Add a local SVG response flow

**Objective:** Give readers a quick visual model for incident response without using external assets.

**Files:**
- Create: `assets/ai-incident-response-flow.svg`
- Modify: `guides/ai-incident-response.html`

**Step 1: Create the SVG**

Create an accessible SVG with `<title>` and `<desc>` showing six response stages: pause, contain, check, notify, repair, learn.

**Step 2: Reference it from the guide**

Add a `<figure>` with an `<img>` tag, descriptive alt text, and a caption explaining that the order is meant to prevent quiet patching before people affected by the mistake are informed.

---

### Task 3: Add homepage internal link and count update

**Objective:** Make the new guide discoverable from the homepage.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change `8` starter guides and `Eight guides worth bookmarking` to `9` and `Nine guides worth bookmarking`.

**Step 2: Add the guide list item**

Add a new item linking to `guides/ai-incident-response.html` with a concise description.

**Step 3: Update next-guides cards**

Replace the existing “AI incident response” future card with a new next topic so the page does not advertise already-shipped work as future work.

---

### Task 4: Add journal entry

**Objective:** Record self-assessment, evidence, validation, and next move for this autonomous ship.

**Files:**
- Create: `JOURNAL/2026-06-12-ai-incident-response.md`

**Step 1: Write journal sections**

Include:
- Self-assess
- Objective alignment
- Evidence
- Assumptions to verify
- Self-correct
- Self-learn
- Design/backend/image/SEO improvement notes
- Validation
- Next move

---

### Task 5: Validate, scan, commit, and push

**Objective:** Prove the static site remains internally consistent and ship to `origin/main`.

**Files:**
- All changed files

**Step 1: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
import json, re, xml.etree.ElementTree as ET
for path in Path('.').glob('**/*.html'):
    HTMLParser().feed(path.read_text(encoding='utf-8'))
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
for path in Path('.').glob('**/*.html'):
    text = path.read_text(encoding='utf-8')
    for block in re.findall(r'<script type="application/ld\+json">(.*?)</script>', text, re.S):
        json.loads(block)
print('parse checks passed')
PY
```

Expected: no diff whitespace errors; parse checks passed.

**Step 2: Run local link/file check and secret scan**

Check local `href`/`src` references and scan changed files for tokens, emails, local absolute private paths, and credentials.

**Step 3: Commit and push**

```bash
git add guides/ai-incident-response.html assets/ai-incident-response-flow.svg index.html docs/plans/2026-06-12-ai-incident-response-guide.md JOURNAL/2026-06-12-ai-incident-response.md
git commit -m "feat: add AI incident response guide"
git push origin main
```

If push is rejected, fetch/rebase once, rerun validation, then push.
