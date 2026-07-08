# AI System Owner Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language guide that helps teams name an accountable owner for each AI workflow, define pause authority, and connect ownership to review, appeals, incidents, and audit trails.

**Architecture:** Keep the project static and dependency-free. Add one HTML guide, one local SVG diagram, homepage count/link updates, and one journal entry. Reuse existing guide conventions: inline CSS, semantic sections, Article JSON-LD, accessible figure, checklist/table content, source links, and print styles.

**Tech Stack:** Static HTML5, inline CSS, local SVG, schema.org Article JSON-LD, Python standard-library validation scripts, Git/GitHub.

---

### Task 1: Create the owner checklist guide shell

**Objective:** Add a new accessible guide page with metadata, JSON-LD, and opening short answer.

**Files:**
- Create: `guides/ai-system-owner-checklist.html`

**Step 1: Write the guide shell**

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>AI System Owner Checklist | Civic AI Field Guide</title>
  <meta name="description" content="A practical checklist for naming who owns an AI workflow, who can pause it, and who must answer when people need review, appeal, or correction.">
</head>
<body>
<main>
  <nav><a href="../index.html">← Civic AI Field Guide</a></nav>
  <p class="eyebrow">AI governance</p>
  <h1>AI system owner checklist.</h1>
  <p class="lead">Use this before an AI tool becomes a routine workflow, policy, classroom practice, public-service step, or vendor-managed decision aid.</p>
</main>
</body>
</html>
```

**Step 2: Verify parse**

Run: `python3 - <<'PY'\nfrom html.parser import HTMLParser\nHTMLParser().feed(open('guides/ai-system-owner-checklist.html').read())\nprint('ok')\nPY`

Expected: `ok`

**Step 3: Commit**

```bash
git add guides/ai-system-owner-checklist.html
git commit -m "feat: add AI system owner guide shell"
```

---

### Task 2: Add source-backed checklist content

**Objective:** Fill the guide with practical ownership fields, RACI-style roles, pause authority, vendor-change triggers, bad signs, and sources.

**Files:**
- Modify: `guides/ai-system-owner-checklist.html`

**Step 1: Add complete sections**

Include sections for:
- short answer;
- why ownership matters;
- the five names every workflow needs;
- owner decision table;
- pause authority;
- handoff and vendor-change triggers;
- questions for the named owner;
- bad signs;
- starter checklist;
- sources.

**Step 2: Run source reachability check**

Run an inline `urllib.request` check for the source URLs.

Expected: all cited source URLs return HTTP 200.

**Step 3: Commit**

```bash
git add guides/ai-system-owner-checklist.html
git commit -m "feat: add AI system owner checklist guidance"
```

---

### Task 3: Add an accessible local SVG diagram

**Objective:** Provide a lightweight visual showing owner, reviewers, pause path, affected people, and correction loop.

**Files:**
- Create: `assets/ai-system-owner-checklist.svg`
- Modify: `guides/ai-system-owner-checklist.html`

**Step 1: Create SVG**

Create a local rights-safe SVG with `<title>` and `<desc>`, no external assets, and clear labels: owner, use case, reviewers, affected people, pause/correct.

**Step 2: Embed figure**

```html
<figure>
  <img src="../assets/ai-system-owner-checklist.svg" alt="A diagram showing an AI workflow owner connected to human reviewers, affected people, a pause path, and a correction loop.">
  <figcaption>Ownership is not just a name on a spreadsheet: the owner must be able to answer questions, pause use, and make corrections stick.</figcaption>
</figure>
```

**Step 3: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-system-owner-checklist.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

**Step 4: Commit**

```bash
git add assets/ai-system-owner-checklist.svg guides/ai-system-owner-checklist.html
git commit -m "feat: add AI ownership diagram"
```

---

### Task 4: Update homepage discoverability

**Objective:** Link the new guide from the homepage and keep guide counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change homepage count copy from `19`/`Nineteen` to `20`/`Twenty`.

**Step 2: Add guide list entry**

Add a final ordered-list item:

```html
<li>
  <div>
    <h3><a href="guides/ai-system-owner-checklist.html">AI system owner checklist</a></h3>
    <p>A lightweight way to name who owns an AI workflow, who can pause it, and who must answer questions when something goes wrong.</p>
  </div>
</li>
```

**Step 3: Refresh next-topic cards**

Replace the completed next-topic card with a new candidate such as `AI policy meeting agenda` or `AI public notice template`.

**Step 4: Commit**

```bash
git add index.html
git commit -m "feat: link AI system owner checklist from homepage"
```

---

### Task 5: Add journal and validate

**Objective:** Record self-assessment, evidence, assumptions, and validation before publishing.

**Files:**
- Create: `JOURNAL/2026-07-08-ai-system-owner-checklist.md`

**Step 1: Create journal entry**

Include required sections: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
for path in Path('.').glob('**/*.html'):
    HTMLParser().feed(path.read_text(encoding='utf-8'))
print('html ok')
PY
python3 - <<'PY'
from pathlib import Path
import json, re
count=0
for path in Path('.').glob('**/*.html'):
    text=path.read_text(encoding='utf-8')
    for m in re.finditer(r'<script type="application/ld\+json">(.*?)</script>', text, re.S):
        json.loads(m.group(1)); count += 1
print(f'json-ld ok: {count}')
PY
python3 - <<'PY'
from pathlib import Path
import xml.etree.ElementTree as ET
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('svg ok')
PY
```

Expected: all commands pass.

**Step 3: Scan changed files for private information**

Run a conservative scan over changed files for local paths, credentials, tokens, emails, and private operator details. Expected: no findings except public donation addresses already intentionally present in existing support copy.

**Step 4: Commit**

```bash
git add JOURNAL/2026-07-08-ai-system-owner-checklist.md docs/plans/2026-07-08-ai-system-owner-checklist.md guides/ai-system-owner-checklist.html assets/ai-system-owner-checklist.svg index.html
git commit -m "feat: add AI system owner checklist"
```
