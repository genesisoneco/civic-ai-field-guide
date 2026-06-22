# AI Procurement Red Flags Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Build a source-backed public guide that helps readers spot risky AI procurement claims before buying, renewing, or expanding AI products.

**Architecture:** Add one static HTML guide, one local rights-safe SVG, homepage internal links, and a journal entry. Keep the existing no-build static architecture and reuse the guide page pattern already present in `guides/`.

**Tech Stack:** Static HTML, inline CSS, SVG, JSON-LD Article structured data, Python standard-library validation.

---

### Task 1: Add the procurement guide page

**Objective:** Create a plain-language checklist for vendor red flags with citations and print-friendly layout.

**Files:**
- Create: `guides/ai-procurement-red-flags.html`
- Reference: `guides/ai-accessibility-review.html`

**Step 1: Write the page**

Create `guides/ai-procurement-red-flags.html` with:
- title: `AI Procurement Red Flags | Civic AI Field Guide`
- meta description focused on buying, renewing, or expanding AI products
- JSON-LD `Article`
- a short-answer section defining AI procurement red flags
- ten red flags covering vague claims, weak evaluation, data terms, accountability, recourse, accessibility, security, contract inspection/exit, and stop rules
- a vendor question script
- source list citing NIST AI RMF, NIST AI RMF Playbook, OECD AI Principles, European Commission AI Act overview, UK AI procurement guidelines, ISO/IEC 42001 overview, and WCAG 2.2

**Step 2: Verify syntax manually**

Run: `python3 - <<'PY' ... HTMLParser over guides/ai-procurement-red-flags.html ... PY`
Expected: parser completes without exception.

**Step 3: Commit later with the full ship**

Do not commit until the homepage, asset, journal, and validation are complete.

---

### Task 2: Add the visual checkpoint asset

**Objective:** Create a rights-safe local SVG that explains the procurement evidence checkpoint.

**Files:**
- Create: `assets/ai-procurement-red-flags.svg`

**Step 1: Create SVG**

Create an SVG with:
- `<title>` and `<desc>`
- a checkpoint flow for claims, evidence, data, safeguards, recourse, and stop rules
- no external images, fonts, or rights-restricted assets

**Step 2: Reference it from the guide**

Ensure the guide uses:

```html
<img src="../assets/ai-procurement-red-flags.svg" alt="A procurement checkpoint diagram showing vendor claims, evidence, data, safeguards, recourse, and stop rules before an AI contract.">
```

**Step 3: Verify SVG parse**

Run XML parsing over all `assets/*.svg`.
Expected: all SVG files parse successfully.

---

### Task 3: Link the new guide from the homepage

**Objective:** Make the page discoverable and update counts ethically.

**Files:**
- Modify: `index.html`

**Step 1: Update count and heading**

Change starter guide count from 12 to 13 and heading from “Twelve guides” to “Thirteen guides.”

**Step 2: Add guide list item**

Add a list item linking to `guides/ai-procurement-red-flags.html` with a short, accurate description.

**Step 3: Update next-topic cards**

Remove “AI procurement red flags” from future topics and replace it with “AI evaluation evidence checklist.”

---

### Task 4: Add the run journal

**Objective:** Record self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-06-22-ai-procurement-red-flags.md`

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

**Step 2: Include source-check note**

Record which cited URLs returned HTTP 200 from this environment.

---

### Task 5: Validate, scan, commit, and push

**Objective:** Ship safely to `origin/main`.

**Files:**
- Validate all changed files.

**Step 1: Run validation**

Run:

```bash
git diff --check
python3 - <<'PY'
# parse HTML, check local href/src, parse SVG, parse JSON-LD
PY
```

Expected: all checks pass.

**Step 2: Scan changed content for private information**

Run a grep-style scan over changed files for secrets, credentials, absolute private paths, emails, and tokens.
Expected: no findings except public donation addresses already present if scanning `index.html`.

**Step 3: Commit**

```bash
git add index.html guides/ai-procurement-red-flags.html assets/ai-procurement-red-flags.svg docs/plans/2026-06-22-ai-procurement-red-flags.md JOURNAL/2026-06-22-ai-procurement-red-flags.md
git commit -m "feat: add AI procurement red flags guide"
```

**Step 4: Push**

```bash
git push origin main
```

If rejected, run `git fetch origin main`, `git rebase origin/main`, rerun validation, then push once more. Do not force-push.
