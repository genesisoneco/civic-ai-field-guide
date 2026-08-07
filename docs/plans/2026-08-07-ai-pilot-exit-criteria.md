# AI Pilot Exit Criteria Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed checklist that helps civic teams decide whether an AI pilot should expand, narrow, pause, or stop after evidence review.

**Architecture:** Keep the site static and follow the established guide pattern: one standalone HTML guide, one local SVG visual, homepage discovery updates, and a journal entry. The guide will translate pilot results into practical decision gates, stop rules, and evidence records without implying that every AI pilot should either scale or fail.

**Tech Stack:** Static HTML, inline CSS, local SVG, JSON-LD Article metadata, Python standard-library validation scripts, GitHub Pages.

---

### Task 1: Create the implementation plan

**Objective:** Document the intended change before editing public content.

**Files:**
- Create: `docs/plans/2026-08-07-ai-pilot-exit-criteria.md`

**Step 1: Write this plan**

Create this Markdown file with goal, architecture, task list, source plan, validation plan, and commit instructions.

**Step 2: Verify the file exists**

Run: `test -f docs/plans/2026-08-07-ai-pilot-exit-criteria.md`
Expected: exit code 0.

**Step 3: Commit later with the full ship**

Do not commit yet; include this file with the guide, asset, homepage update, and journal.

---

### Task 2: Create the SVG exit-decision visual

**Objective:** Add a rights-safe visual that helps readers remember the four possible pilot decisions.

**Files:**
- Create: `assets/ai-pilot-exit-criteria.svg`

**Step 1: Write the SVG**

Use a local SVG with `<title>` and `<desc>`, four labeled decision paths, high contrast, and no external dependencies.

**Step 2: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-pilot-exit-criteria.svg')\nprint('ok')\nPY`
Expected: `ok`.

---

### Task 3: Add the AI pilot exit criteria guide

**Objective:** Publish a practical checklist that helps teams turn pilot evidence into a clear expand, narrow, pause, or stop decision.

**Files:**
- Create: `guides/ai-pilot-exit-criteria.html`

**Step 1: Add a standalone guide page**

Include:
- title and meta description
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-08-07`
- short answer
- SVG figure with descriptive alt text and caption
- source-backed explanation of why exit criteria matter
- before-pilot exit criteria table
- decision gate table
- evidence packet checklist
- meeting workflow
- stop rules
- starter language
- related internal links
- sources and disclaimer

**Step 2: Use these sources**

Cite only public source URLs checked during the run:
- `https://www.nist.gov/itl/ai-risk-management-framework`
- `https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf`
- `https://digital-strategy.ec.europa.eu/en/library/ethics-guidelines-trustworthy-ai`
- `https://www.ftc.gov/business-guidance/blog/keep-your-ai-claims-check`

**Step 3: Verify HTML parses**

Run the repository HTML parser check after all edits.
Expected: all HTML files parse without parser errors.

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable from the homepage.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change `32` starter guides to `33` and “Thirty-two guides worth bookmarking.” to “Thirty-three guides worth bookmarking.”

**Step 2: Add the guide list item**

Append a new list item after the AI benefits-claim review:

```html
<li>
  <div>
    <h3><a href="guides/ai-pilot-exit-criteria.html">AI pilot exit criteria</a></h3>
    <p>A practical checklist for deciding whether an AI pilot should expand, narrow, pause, or stop after evidence review.</p>
  </div>
</li>
```

**Step 3: Update next guides**

Replace the now-shipped next-topic card with a future useful topic, such as “AI policy meeting agenda” plus “AI renewal decision checklist.”

---

### Task 5: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-08-07-ai-pilot-exit-criteria.md`

**Step 1: Write the journal entry**

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

**Step 2: Include validation outcomes**

Document source reachability, diff check, HTML parse, local link/file check, SVG parse, JSON-LD parse, build-tool availability, and secret scan.

---

### Task 6: Validate, scan, commit, and push

**Objective:** Prove the ship is safe and publish it.

**Files:**
- All changed files

**Step 1: Run validation**

Run:

```bash
git diff --check
python3 tools-or-inline-html-parse-check
python3 tools-or-inline-local-link-check
python3 tools-or-inline-svg-parse-check
python3 tools-or-inline-jsonld-check
```

Expected: all checks pass.

**Step 2: Scan changed files for private data**

Run a changed-file scan for tokens, credentials, local private paths, emails, and logs.
Expected: no findings except public donation addresses already present in `index.html` if that file is part of the diff.

**Step 3: Commit and push**

```bash
git add docs/plans/2026-08-07-ai-pilot-exit-criteria.md assets/ai-pilot-exit-criteria.svg guides/ai-pilot-exit-criteria.html index.html JOURNAL/2026-08-07-ai-pilot-exit-criteria.md
git commit -m "feat: add AI pilot exit criteria"
git push origin main
```

If push is rejected, fetch/rebase once, rerun validation, and push again. Do not force-push.
