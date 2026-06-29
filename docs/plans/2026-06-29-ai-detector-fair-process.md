# AI Detector Limits and Fair Process Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed guide that explains why AI writing detectors require caution and gives schools or teams a fair process for suspected AI use.

**Architecture:** Keep the site static and low-maintenance: one HTML guide, one local rights-safe SVG diagram, one homepage link update, and one journal entry. Use source-backed claims, semantic HTML, accessible alt text, and no client-side dependencies.

**Tech Stack:** Static HTML, inline CSS, SVG, JSON-LD Article metadata, Python validation scripts, Git/GitHub.

---

### Task 1: Research detector reliability and fair-process sources

**Objective:** Gather high-quality sources before making public AI claims.

**Files:**
- No code files yet
- Later citations in: `guides/ai-detector-limits-fair-process.html`

**Step 1: Check source reachability**

Run:

```bash
python3 - <<'PY'
import urllib.request
urls = [
  'https://openai.com/index/new-ai-classifier-for-indicating-ai-written-text/',
  'https://help.openai.com/en/articles/8313351-how-can-educators-respond-to-students-presenting-ai-generated-content-as-their-own',
  'https://teaching.cornell.edu/generative-artificial-intelligence/ai-academic-integrity',
  'https://edintegrity.biomedcentral.com/articles/10.1007/s40979-023-00146-z',
  'https://arxiv.org/abs/2304.02819',
  'https://www.unesco.org/en/articles/guidance-generative-ai-education-and-research',
]
for url in urls:
    req = urllib.request.Request(url, headers={'User-Agent': 'Lantern source check'})
    with urllib.request.urlopen(req, timeout=20) as response:
        print(response.status, url)
PY
```

Expected: each source returns `200`.

**Step 2: Extract public-education claims**

Use only claims supported by those sources:

- OpenAI withdrew its classifier due to low accuracy.
- OpenAI warned the classifier was not fully reliable and should not be the primary decision-making tool.
- Independent literature reports that AI-text detection tools vary in performance and can create false positives.
- Liang et al. report bias risk against non-native English writers.
- Education guidance emphasizes clear policy, process, and human judgment.

**Step 3: Commit**

Do not commit research alone unless no content can be produced.

---

### Task 2: Create the local SVG fair-process diagram

**Objective:** Add a rights-safe visual asset that makes the core rule memorable.

**Files:**
- Create: `assets/ai-detector-fair-process.svg`

**Step 1: Write SVG**

Create a diagram with:

- `<title>`: `AI detector caution and fair process path`
- `<desc>` explaining the flow
- Five visual steps: detector flag, check context, talk first, weigh evidence, fair outcome
- Final rule: no automatic penalty from detector score alone

**Step 2: Verify SVG parses**

Run:

```bash
python3 - <<'PY'
from pathlib import Path
import xml.etree.ElementTree as ET
ET.parse(Path('assets/ai-detector-fair-process.svg'))
print('svg ok')
PY
```

Expected: `svg ok`.

**Step 3: Commit**

Commit together with the guide in Task 3.

---

### Task 3: Create the AI detector fair-process guide

**Objective:** Publish a practical, source-backed page that reduces overreliance on detector scores.

**Files:**
- Create: `guides/ai-detector-limits-fair-process.html`

**Step 1: Add page structure**

Include:

- Title: `AI Detector Limits and Fair Process | Civic AI Field Guide`
- Meta description for the search intent “AI detector limits” and “fair process”
- JSON-LD Article with `datePublished` and `dateModified` set to `2026-06-29`
- Plain-language lead
- Short answer card
- Diagram figure using `../assets/ai-detector-fair-process.svg`
- Sections on caution, minimum fair-process rule, review path, evidence strength, conversation script, better workflow design, and sources

**Step 2: Keep claims narrow**

Do not claim all detectors are useless. Say:

```html
<p>An <strong>AI writing detector</strong> can be one signal, but it should not be the whole case. <mark>No one should face an automatic penalty from a detector result alone.</mark></p>
```

**Step 3: Verify page parses**

Run:

```bash
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
class Parser(HTMLParser): pass
Parser().feed(Path('guides/ai-detector-limits-fair-process.html').read_text())
print('html ok')
PY
```

Expected: `html ok`.

**Step 4: Commit**

Commit together with Tasks 2 and 4.

---

### Task 4: Add homepage discovery links

**Objective:** Make the new guide discoverable from the site homepage.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change:

```html
<div class="metric"><b>15</b><span>starter guides</span></div>
```

to:

```html
<div class="metric"><b>16</b><span>starter guides</span></div>
```

Change:

```html
<h2>Fifteen guides worth bookmarking.</h2>
```

to:

```html
<h2>Sixteen guides worth bookmarking.</h2>
```

**Step 2: Add guide list item**

Add after the AI evaluation evidence checklist item:

```html
<li>
  <div>
    <h3><a href="guides/ai-detector-limits-fair-process.html">AI detector limits and fair process</a></h3>
    <p>A source-backed guide to why AI writing detectors need caution and how to handle suspected AI use without shortcut accusations.</p>
  </div>
</li>
```

**Step 3: Rotate next-guide cards**

Replace the completed detector card with a future useful topic:

```html
<article class="card"><h3>AI translation and language access</h3><p>A practical guide to using AI translation carefully without erasing human review, cultural context, or accessibility needs.</p></article>
```

**Step 4: Commit**

Commit together with the guide.

---

### Task 5: Add journal entry and validate

**Objective:** Record the self-assessment and verify the ship before pushing.

**Files:**
- Create: `JOURNAL/2026-06-29-ai-detector-fair-process.md`

**Step 1: Add journal sections**

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

**Step 2: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
class Parser(HTMLParser): pass
for path in Path('.').glob('**/*.html'):
    Parser().feed(path.read_text())
print('html parse ok')
PY
python3 - <<'PY'
from pathlib import Path
import xml.etree.ElementTree as ET
for path in Path('assets').glob('*.svg'):
    ET.parse(path)
print('svg parse ok')
PY
```

Expected: all pass.

**Step 3: Check local links and JSON-LD**

Run repository local-link and JSON-LD validation scripts or inline Python equivalents.

Expected: all local `href`/`src` references resolve and JSON-LD parses.

**Step 4: Scan for secrets/private info**

Run a changed-file scan for token-like strings, credentials, emails, and absolute private local paths.

Expected: no findings.

**Step 5: Commit**

```bash
git add index.html guides/ai-detector-limits-fair-process.html assets/ai-detector-fair-process.svg docs/plans/2026-06-29-ai-detector-fair-process.md JOURNAL/2026-06-29-ai-detector-fair-process.md
git commit -m "feat: add AI detector fair process guide"
```

---

### Task 6: Push safely

**Objective:** Publish the ship to `origin/main` without overwriting remote work.

**Files:**
- No additional files

**Step 1: Push**

Run:

```bash
git push origin main
```

Expected: push succeeds.

**Step 2: If rejected**

Run once:

```bash
git fetch origin main
git rebase origin/main
# re-run validation
git push origin main
```

Expected: push succeeds or stops with the full error text if validation/rebase fails.
