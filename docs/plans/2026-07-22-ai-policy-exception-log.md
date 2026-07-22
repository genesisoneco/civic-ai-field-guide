# AI Policy Exception Log Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a practical, source-backed guide that helps teams document temporary exceptions to AI policies without normalizing silent noncompliance.

**Architecture:** Keep the project static and auditable: one standalone HTML guide, one local rights-safe SVG diagram, homepage count/link updates, and one journal entry. Reuse the existing Civic AI Field Guide pattern for inline CSS, semantic sections, Article JSON-LD, accessible image text, internal links, and source lists.

**Tech Stack:** Static HTML, inline CSS, SVG, schema.org Article JSON-LD, Python standard-library validation, Git.

---

### Task 1: Verify sources

**Objective:** Ground governance, accountability, privacy, security, and lifecycle claims before writing public content.

**Files:**
- No file changes

**Step 1: Check source reachability**

Run:
```bash
cd civic-ai-field-guide
python3 - <<'PY'
import urllib.request
urls = [
  'https://www.nist.gov/itl/ai-risk-management-framework',
  'https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf',
  'https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf',
  'https://www.cisa.gov/resources-tools/resources/secure-by-design',
  'https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/',
]
for url in urls:
    req = urllib.request.Request(url, headers={'User-Agent': 'LanternCivicAIFieldGuide/1.0'})
    with urllib.request.urlopen(req, timeout=25) as response:
        print(response.status, url)
PY
```
Expected: five `200` lines.

**Step 2: Commit**

No commit for research-only task.

---

### Task 2: Add exception log SVG

**Objective:** Create a local visual that makes the exception lifecycle understandable at a glance.

**Files:**
- Create: `assets/ai-policy-exception-log.svg`

**Step 1: Create the SVG**

Add an accessible SVG with a title, description, and a five-step flow: request, risk, approval, expiry, review/close.

**Step 2: Verify SVG parses**

Run:
```bash
python3 - <<'PY'
import xml.etree.ElementTree as ET
ET.parse('assets/ai-policy-exception-log.svg')
print('svg ok')
PY
```
Expected: `svg ok`.

**Step 3: Commit**

```bash
git add assets/ai-policy-exception-log.svg
git commit -m "feat: add AI policy exception log diagram"
```

---

### Task 3: Add the guide page

**Objective:** Publish a concise guide and starter log template for time-boxing policy exceptions.

**Files:**
- Create: `guides/ai-policy-exception-log.html`

**Step 1: Write the HTML guide**

Include:
- SEO title and meta description.
- Article JSON-LD with date `2026-07-22` and image `../assets/ai-policy-exception-log.svg`.
- Short answer explaining that an exception log is not permission to ignore policy.
- Sections for when to log an exception, what fields to record, safeguards, expiry/review rules, bad signs, starter language, and sources.
- Internal links to risk register, system owner, audit trail, incident response, public notice, model update review, data minimization, retention, and deletion request guides.
- Accessible image alt text and caption.

**Step 2: Verify HTML parses**

Run:
```bash
python3 - <<'PY'
from html.parser import HTMLParser
HTMLParser().feed(open('guides/ai-policy-exception-log.html', encoding='utf-8').read())
print('html ok')
PY
```
Expected: `html ok`.

**Step 3: Commit**

```bash
git add guides/ai-policy-exception-log.html
git commit -m "feat: add AI policy exception log guide"
```

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable and keep public counts current.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change the hero metric and section heading from 25 to 26 guides.

**Step 2: Add guide list item**

Add a list item after the AI model update review guide linking to `guides/ai-policy-exception-log.html`.

**Step 3: Refresh next-guide cards**

Replace the now-completed “AI policy exception log” card with a next useful topic: “AI policy meeting agenda.” Keep a distinct card for “AI document intake checklist” and the documents card.

**Step 4: Commit**

```bash
git add index.html
git commit -m "chore: link AI policy exception log"
```

---

### Task 5: Add journal entry

**Objective:** Record the ship’s self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-07-22-ai-policy-exception-log.md`

**Step 1: Write journal**

Include required headings: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Commit**

```bash
git add JOURNAL/2026-07-22-ai-policy-exception-log.md
git commit -m "docs: journal AI policy exception log ship"
```

---

### Task 6: Validate and push

**Objective:** Confirm site references are coherent, scan changed files for private data, then publish.

**Files:**
- All changed files

**Step 1: Run validation**

Run `git diff --check`, parse all HTML, verify relative HTML references, parse SVG files, parse JSON-LD blocks, and scan changed files for secrets/private paths.

**Step 2: Push safely**

Run:
```bash
git status --short --branch
git push origin main
```
If push is rejected, run `git fetch origin main`, `git rebase origin/main`, re-run validation, then push once more.
