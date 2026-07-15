# AI Record Retention Schedule Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed public guide that helps teams decide how long to keep AI prompts, uploads, outputs, logs, evaluations, incidents, appeals, and deletion evidence.

**Architecture:** Keep the site static and auditable: one standalone HTML guide, one local rights-safe SVG diagram, homepage index updates, and one journal entry. Avoid new dependencies or backend code.

**Tech Stack:** Static HTML, inline CSS, SVG, schema.org Article JSON-LD, Python validation scripts, Git.

---

### Task 1: Create the retention schedule guide

**Objective:** Publish a practical, source-backed guide with a starter retention table and policy language.

**Files:**
- Create: `guides/ai-record-retention-schedule.html`

**Step 1: Write the guide HTML**

Use the same standalone page pattern as `guides/ai-data-minimization-checklist.html`. Include:
- Title: `AI Record Retention Schedule | Civic AI Field Guide`
- Meta description focused on prompts, uploads, outputs, logs, evaluations, incidents, appeals, and deletion records.
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-07-15`.
- Sections: short answer, diagram figure, why AI needs retention questions, first-pass checklist, starter schedule table, practical retention patterns, bad signs, starter policy language, sources.
- Sources: NIST Privacy Framework, ICO storage limitation, NIST AI RMF page and PDF, OMB M-24-10, NARA records-management contract language.

**Step 2: Verify source framing**

Run: `python3` URL reachability check for each cited source.
Expected: HTTP 200 for all six cited URLs.

**Step 3: Commit-ready check**

Run: `git diff -- guides/ai-record-retention-schedule.html`
Expected: New guide only; no private paths, credentials, or unsupported factual claims.

### Task 2: Add the retention lifecycle diagram

**Objective:** Add a rights-safe visual explaining creation, use, review, archive/delete, and deletion evidence.

**Files:**
- Create: `assets/ai-record-retention-schedule.svg`

**Step 1: Create the SVG**

Include `<title>` and `<desc>`, a lifecycle timeline, and labels for schedule fields.

**Step 2: Verify parseability**

Run: XML parse validation for `assets/ai-record-retention-schedule.svg`.
Expected: PASS.

### Task 3: Update homepage discovery

**Objective:** Link the new guide from the homepage and keep guide counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change `22` starter guides and `Twenty-two guides` to `23` and `Twenty-three guides`.

**Step 2: Add guide list item**

Append `AI record retention schedule` after the data minimization checklist with a short description.

**Step 3: Refresh next-topic cards**

Remove the now-built retention card and add a new next topic: AI policy meeting agenda and AI deletion request workflow.

### Task 4: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-07-15-ai-record-retention-schedule.md`

**Step 1: Write the entry**

Include required headings: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Confirm blocker status**

State that no full site build tool is present if validation confirms no build command exists.

### Task 5: Validate, commit, and push

**Objective:** Ship safely to `origin/main`.

**Files:**
- Validate all changed files.

**Step 1: Run validation**

Run:
```bash
git diff --check
python3 - <<'PY'
# parse HTML, local href/src references, SVG XML, JSON-LD, and scan changed files for private paths/secrets
PY
```
Expected: all checks pass.

**Step 2: Commit**

```bash
git add index.html guides/ai-record-retention-schedule.html assets/ai-record-retention-schedule.svg docs/plans/2026-07-15-ai-record-retention-schedule.md JOURNAL/2026-07-15-ai-record-retention-schedule.md
git commit -m "feat: add AI record retention schedule"
```

**Step 3: Push**

```bash
git push origin main
```

Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, then push.
