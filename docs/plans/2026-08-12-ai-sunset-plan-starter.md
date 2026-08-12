# AI Sunset Plan Starter Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed public guide that helps civic teams end, replace, or archive an AI workflow without losing records, continuity, data accountability, or public trust.

**Architecture:** This is a static-site content ship following the existing guide pattern: one standalone HTML guide, one local rights-safe SVG visual, homepage discovery updates, and a journal entry. No backend, dependencies, or build tooling are introduced.

**Tech Stack:** Static HTML, inline CSS, local SVG, JSON-LD Article metadata, git.

---

### Task 1: Add the AI sunset guide page

**Objective:** Create a standalone, source-backed guide for AI offboarding and shutdown planning.

**Files:**
- Create: `guides/ai-sunset-plan-starter.html`

**Step 1: Write the page**

Create `guides/ai-sunset-plan-starter.html` with:
- Title: `AI Sunset Plan Starter | Civic AI Field Guide`
- Meta description about ending, replacing, or archiving an AI workflow.
- JSON-LD Article block with `datePublished` and `dateModified` set to `2026-08-12`.
- Sections: short answer, why sunset planning matters, triggers, six-step shutdown sequence, continuity, records/data/secrets, starter memo language, stop rules, related pages, sources.
- Sources: NIST AI RMF, OMB M-24-10, NARA records scheduling and GRS, CISA Secure by Design, FTC data breach response guide.
- Internal links to renewal decision, pilot exit, record retention, deletion request, risk register, public notice, and appeal path pages.

**Step 2: Verify source-backed claims**

Run:

```bash
python3 - <<'PY'
import urllib.request
urls=[
'https://www.nist.gov/itl/ai-risk-management-framework',
'https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf',
'https://www.archives.gov/records-mgmt/scheduling',
'https://www.archives.gov/records-mgmt/grs',
'https://www.cisa.gov/resources-tools/resources/secure-by-design',
'https://www.ftc.gov/business-guidance/resources/data-breach-response-guide-business',
]
for u in urls:
    req=urllib.request.Request(u, method='HEAD', headers={'User-Agent':'LanternSourceCheck/1.0'})
    try:
        with urllib.request.urlopen(req, timeout=20) as r:
            print(r.status, u)
    except Exception:
        req=urllib.request.Request(u, headers={'User-Agent':'LanternSourceCheck/1.0'})
        with urllib.request.urlopen(req, timeout=20) as r:
            print(r.status, u)
PY
```

Expected: all cited URLs return HTTP 200.

**Step 3: Commit**

```bash
git add guides/ai-sunset-plan-starter.html
git commit -m "feat: add AI sunset plan starter"
```

### Task 2: Add the local SVG visual

**Objective:** Provide a rights-safe visual that makes the shutdown sequence scannable.

**Files:**
- Create: `assets/ai-sunset-plan-starter.svg`
- Modify: `guides/ai-sunset-plan-starter.html`

**Step 1: Create the SVG**

Create `assets/ai-sunset-plan-starter.svg` as a local SVG with:
- `<title>AI sunset plan sequence</title>`
- `<desc>A six-step path for sunsetting an AI system: decide, freeze, preserve, transition, dispose, and review.</desc>`
- Six labeled nodes: Decide, Freeze, Preserve, Transition, Dispose, Review.

**Step 2: Reference the SVG in the guide**

In `guides/ai-sunset-plan-starter.html`, add:

```html
<figure>
  <img src="../assets/ai-sunset-plan-starter.svg" alt="A six-step AI sunset plan path: decide, freeze, preserve, transition, delete or archive, and review.">
  <figcaption>A sunset plan turns an ending into a controlled handoff: decision record, change freeze, records, continuity, data disposition, and lessons learned.</figcaption>
</figure>
```

**Step 3: Commit**

```bash
git add assets/ai-sunset-plan-starter.svg guides/ai-sunset-plan-starter.html
git commit -m "design: add AI sunset plan visual"
```

### Task 3: Update homepage discovery

**Objective:** Make the new guide discoverable and keep homepage counts current.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change homepage guide count text from 34 to 35 in:
- hero metric
- guide section heading

**Step 2: Add guide list item**

Append a new `<li>` after the renewal decision checklist item:

```html
<li>
  <div>
    <h3><a href="guides/ai-sunset-plan-starter.html">AI sunset plan starter</a></h3>
    <p>A practical template for ending, replacing, or archiving an AI workflow while preserving records, continuity, notices, data handling, and accountability.</p>
  </div>
</li>
```

**Step 3: Update next-guide cards**

Replace the prior AI sunset plan card with a new next-topic card, such as `AI policy meeting agenda`, while preserving the documents card.

**Step 4: Commit**

```bash
git add index.html
git commit -m "seo: link AI sunset plan from homepage"
```

### Task 4: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, SEO/design notes, and next move.

**Files:**
- Create: `JOURNAL/2026-08-12-ai-sunset-plan-starter.md`

**Step 1: Write journal entry**

Include the required sections:
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
git add JOURNAL/2026-08-12-ai-sunset-plan-starter.md
git commit -m "docs: add journal for AI sunset plan"
```

### Task 5: Validate and ship

**Objective:** Verify static content integrity before pushing.

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
root=Path('.')
for p in root.rglob('*.html'):
    HTMLParser().feed(p.read_text(encoding='utf-8'))
for p in root.rglob('*.svg'):
    ET.parse(p)
for p in root.rglob('*.html'):
    text=p.read_text(encoding='utf-8')
    for m in re.finditer(r'<script type="application/ld\+json">(.*?)</script>', text, re.S):
        json.loads(m.group(1))
print('static parse checks passed')
PY
python3 tools_or_inline_internal_link_check.py
```

Expected: no trailing whitespace errors; HTML, SVG, JSON-LD, and local link checks pass.

**Step 2: Scan changed files for secrets/private local paths**

Run a conservative scan over staged content for token-like strings, local private paths, and operator-only details. Expected: no secrets or private operator data found; public donation addresses already present are not newly introduced secrets.

**Step 3: Push safely**

```bash
git status --short --branch
git push origin main
```

If rejected, run:

```bash
git fetch origin main
git rebase origin/main
# rerun validation
git push origin main
```

Stop and report any rebase conflicts or new validation errors.
