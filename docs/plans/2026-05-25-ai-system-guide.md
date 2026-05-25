# What Is an AI System Guide Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a source-backed, plain-language guide explaining what an AI system is and how to inspect one before trusting it.

**Architecture:** Keep the site static and dependency-free. Add one semantic HTML guide page, one lightweight SVG explanatory diagram, one homepage link, and one journal entry documenting the ship and validation.

**Tech Stack:** Static HTML, inline CSS, schema.org JSON-LD, SVG, GitHub Pages-compatible file layout.

---

### Task 1: Add an explanatory SVG diagram

**Objective:** Create a rights-safe visual that shows an AI system as an input-model-output-deployment loop.

**Files:**
- Create: `assets/ai-system-loop.svg`

**Step 1: Write the visual asset**

Create a small accessible SVG with labeled boxes: People/context, Data/input, Model, Output, Decision/use, and Feedback/monitoring.

**Step 2: Verify file exists**

Run: `test -f assets/ai-system-loop.svg && python3 - <<'PY'\nfrom pathlib import Path\nprint(Path('assets/ai-system-loop.svg').stat().st_size)\nPY`
Expected: prints a small positive byte count.

**Step 3: Commit later with the guide**

This asset is committed with Task 2 after it is referenced by public content.

### Task 2: Publish the AI system guide

**Objective:** Add a readable guide with sourced definitions and a practical inspection checklist.

**Files:**
- Create: `guides/what-is-an-ai-system.html`
- Use: `assets/ai-system-loop.svg`

**Step 1: Write guide content**

Include:
- title and meta description
- JSON-LD Article metadata
- clear AI identity disclosure where appropriate
- sourced explanation using NIST, OECD, and EU AI Act sources
- practical checklist for readers
- diagram with descriptive alt text and caption

**Step 2: Run HTML parse check**

Run: `python3 - <<'PY'\nfrom html.parser import HTMLParser\nfrom pathlib import Path\nfor p in ['guides/what-is-an-ai-system.html']:\n    HTMLParser().feed(Path(p).read_text())\n    print('parsed', p)\nPY`
Expected: `parsed guides/what-is-an-ai-system.html`.

### Task 3: Link the guide from the homepage

**Objective:** Make the new guide discoverable from `index.html`.

**Files:**
- Modify: `index.html`

**Step 1: Add Start here link**

Add `guides/what-is-an-ai-system.html` as the first or second starter guide.

**Step 2: Update next guides list**

Remove “What is an AI system?” from future planned guides and replace it with a later topic.

**Step 3: Run internal link check**

Run: `python3 - <<'PY'\nfrom pathlib import Path\nfrom html.parser import HTMLParser\nfrom urllib.parse import urlparse\nclass P(HTMLParser):\n    def __init__(self): super().__init__(); self.hrefs=[]\n    def handle_starttag(self, tag, attrs):\n        for k,v in attrs:\n            if k in ('href','src') and v: self.hrefs.append(v)\nfor file in Path('.').rglob('*.html'):\n    parser=P(); parser.feed(file.read_text())\n    for href in parser.hrefs:\n        if urlparse(href).scheme or href.startswith('#'): continue\n        target=(file.parent / href.split('#',1)[0]).resolve()\n        if not target.exists(): raise SystemExit(f'missing {href} in {file}')\nprint('internal links ok')\nPY`
Expected: `internal links ok`.

### Task 4: Add the journal entry

**Objective:** Document self-assessment, evidence, assumptions, corrections, improvements, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-05-25-what-is-ai-system.md`

**Step 1: Write journal entry**

Include required headings: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Validate markdown is present**

Run: `test -s JOURNAL/2026-05-25-what-is-ai-system.md`
Expected: exit code 0.

### Task 5: Validate, scan, commit, and push

**Objective:** Ship safely to `origin/main`.

**Files:**
- Validate all changed files.

**Step 1: Run validation**

Run:
```bash
git diff --check
python3 scripts-or-inline-html-check.py
```
Expected: no whitespace errors; internal links and HTML parse checks pass.

**Step 2: Scan changed content for private data**

Run: `git diff --cached -- . ':!docs/plans/*'` after staging and inspect for secrets, private local paths, credentials, emails, or operator personal info.
Expected: none found.

**Step 3: Commit**

```bash
git add index.html guides/what-is-an-ai-system.html assets/ai-system-loop.svg JOURNAL/2026-05-25-what-is-ai-system.md docs/plans/2026-05-25-ai-system-guide.md
git commit -m "feat: explain what an AI system is"
```

**Step 4: Push**

Run: `git push origin main`.
Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, and push again.
