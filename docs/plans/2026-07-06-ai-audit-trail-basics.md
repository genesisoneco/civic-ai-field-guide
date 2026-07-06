# AI Audit Trail Basics Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language guide that helps teams record enough about AI-assisted work to reconstruct decisions, review harms, and improve systems without over-collecting personal data.

**Architecture:** Keep the site static and dependency-free. Add one HTML guide, one local SVG diagram, homepage internal links/count updates, and one journal entry. Reuse the existing guide page pattern: inline CSS, semantic sections, Article JSON-LD, accessible figure, checklist/table content, source links, and print styles.

**Tech Stack:** Static HTML5, inline CSS, local SVG, schema.org Article JSON-LD, Python standard-library validation scripts, Git/GitHub.

---

### Task 1: Add the audit trail guide shell

**Objective:** Create a new guide page with accessible metadata, article structure, and a short answer.

**Files:**
- Create: `guides/ai-audit-trail-basics.html`

**Step 1: Write the HTML shell**

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>AI Audit Trail Basics | Civic AI Field Guide</title>
  <meta name="description" content="A plain-language guide to recording AI use, decisions, review, incidents, and corrections without collecting unnecessary personal data.">
</head>
<body>
<main>
  <nav><a href="../index.html">← Civic AI Field Guide</a></nav>
  <p class="eyebrow">AI accountability</p>
  <h1>AI audit trail basics.</h1>
  <p class="lead">Use this when a team needs to know what to record about AI-assisted work so decisions, incidents, appeals, and corrections can be checked later.</p>
</main>
</body>
</html>
```

**Step 2: Run parse check**

Run: `python3 - <<'PY'\nfrom html.parser import HTMLParser\nHTMLParser().feed(open('guides/ai-audit-trail-basics.html').read())\nprint('ok')\nPY`

Expected: `ok`

**Step 3: Commit**

```bash
git add guides/ai-audit-trail-basics.html
git commit -m "feat: add AI audit trail guide shell"
```

---

### Task 2: Add source-backed guidance content

**Objective:** Fill the guide with practical audit-trail fields, privacy guardrails, review cadence, and public-interest sources.

**Files:**
- Modify: `guides/ai-audit-trail-basics.html`

**Step 1: Add sections**

Add complete sections for:
- short answer;
- why audit trails matter;
- what to record;
- what not to collect;
- minimum record template;
- incident/appeal additions;
- review cadence;
- bad signs;
- starter checklist;
- sources.

**Step 2: Run source reachability check**

Run: `python3 tools-or-inline-source-check.py` or an inline `urllib.request` loop for the five source URLs.

Expected: all five URLs return HTTP 200.

**Step 3: Commit**

```bash
git add guides/ai-audit-trail-basics.html
git commit -m "feat: add source-backed AI audit trail guidance"
```

---

### Task 3: Add an accessible local SVG diagram

**Objective:** Provide a lightweight visual that helps readers understand the record-review-correct loop.

**Files:**
- Create: `assets/ai-audit-trail-basics.svg`
- Modify: `guides/ai-audit-trail-basics.html`

**Step 1: Create SVG**

Create a rights-safe local SVG with `<title>` and `<desc>`, no external assets, and labeled stages: record context, capture AI role, human review, incident/appeal, correction learned.

**Step 2: Embed figure**

```html
<figure>
  <img src="../assets/ai-audit-trail-basics.svg" alt="A five-step AI audit trail loop: record context, capture the AI role, document human review, log incidents or appeals, and feed corrections back into policy.">
  <figcaption>Good audit trails are loops, not filing cabinets: record only what helps people verify, appeal, fix, and learn.</figcaption>
</figure>
```

**Step 3: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-audit-trail-basics.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

**Step 4: Commit**

```bash
git add assets/ai-audit-trail-basics.svg guides/ai-audit-trail-basics.html
git commit -m "feat: add AI audit trail diagram"
```

---

### Task 4: Update homepage internal links and guide count

**Objective:** Make the new guide discoverable from the homepage and keep counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change `18` and `Eighteen` homepage copy to `19` and `Nineteen`.

**Step 2: Add guide list entry**

Add a final ordered-list item:

```html
<li>
  <div>
    <h3><a href="guides/ai-audit-trail-basics.html">AI audit trail basics</a></h3>
    <p>A plain-language guide to what teams should record so AI decisions, incidents, appeals, and corrections can be checked later.</p>
  </div>
</li>
```

**Step 3: Refresh next-topic cards**

Replace the now-completed next-topic card with a future guide candidate such as `AI policy meeting agenda` or `AI system owner checklist`.

**Step 4: Commit**

```bash
git add index.html
git commit -m "feat: link AI audit trail guide from homepage"
```

---

### Task 5: Add journal entry and run validation

**Objective:** Record self-assessment, evidence, assumptions, and validation for the ship.

**Files:**
- Create: `JOURNAL/2026-07-06-ai-audit-trail-basics.md`

**Step 1: Create journal entry**

Include the required sections: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

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
import re, os
for html in Path('.').glob('**/*.html'):
    text = html.read_text(encoding='utf-8')
    for attr in ('href','src'):
        for m in re.finditer(attr + r'="([^"]+)"', text):
            url=m.group(1)
            if url.startswith(('#','http','mailto:','tel:','bitcoin:','ethereum:','solana:','javascript:')):
                continue
            target=(html.parent / url.split('#')[0]).resolve()
            if url.split('#')[0] and not target.exists():
                raise SystemExit(f'missing {attr}: {html} -> {url}')
print('local links ok')
PY
python3 - <<'PY'
from pathlib import Path
import xml.etree.ElementTree as ET
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('svg ok')
PY
```

Expected: all pass.

**Step 3: Scan changed files for secrets/private data**

Run a targeted scan for token-like strings, absolute local private paths, and operator details in changed files. Expected: no findings.

**Step 4: Commit and push**

```bash
git add JOURNAL/2026-07-06-ai-audit-trail-basics.md docs/plans/2026-07-06-ai-audit-trail-basics.md guides/ai-audit-trail-basics.html assets/ai-audit-trail-basics.svg index.html
git commit -m "feat: add AI audit trail basics guide"
git push origin main
```
