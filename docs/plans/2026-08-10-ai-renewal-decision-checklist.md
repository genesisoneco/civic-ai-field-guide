# AI Renewal Decision Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed checklist that helps civic teams decide whether an AI contract or deployed AI workflow should renew, renegotiate, narrow, pause, or end after real-world use.

**Architecture:** Keep the project as a static GitHub Pages site and follow the established guide pattern: one standalone HTML guide, one local SVG visual, homepage discovery updates, and a journal entry. The page will connect renewal decisions to evidence, monitoring, incidents, vendor changes, costs, accessibility, and exit options without giving legal or procurement advice.

**Tech Stack:** Static HTML, inline CSS, local SVG, JSON-LD Article metadata, Python standard-library validation scripts, GitHub Pages.

---

### Task 1: Create the implementation plan

**Objective:** Document the intended change before editing public content.

**Files:**
- Create: `docs/plans/2026-08-10-ai-renewal-decision-checklist.md`

**Step 1: Write this plan**

Create this Markdown file with the goal, architecture, source plan, guide tasks, validation plan, and commit instructions.

**Step 2: Verify the file exists**

Run: `test -f docs/plans/2026-08-10-ai-renewal-decision-checklist.md`
Expected: exit code 0.

**Step 3: Commit later with the full ship**

Do not commit yet; include this file with the guide, asset, homepage update, and journal.

---

### Task 2: Create the SVG renewal-decision visual

**Objective:** Add a rights-safe visual that makes the renewal gates easy to remember.

**Files:**
- Create: `assets/ai-renewal-decision-checklist.svg`

**Step 1: Write the SVG**

Use a local SVG with `<title>` and `<desc>`, five labeled decision paths, high contrast, and no external dependencies.

**Step 2: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-renewal-decision-checklist.svg')\nprint('ok')\nPY`
Expected: `ok`.

---

### Task 3: Add the AI renewal decision checklist guide

**Objective:** Publish a practical renewal review that teams can use before contracts, budgets, or deployed AI workflows roll forward.

**Files:**
- Create: `guides/ai-renewal-decision-checklist.html`

**Step 1: Add a standalone guide page**

Include:
- title and meta description
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-08-10`
- short answer
- SVG figure with descriptive alt text and caption
- source-backed explanation of why renewal review matters
- renewal evidence packet checklist
- vendor/workflow change review table
- five decision gates: renew, renegotiate, narrow, pause, end
- renewal meeting agenda
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

**Objective:** Make the new guide discoverable from the homepage and keep the next-topic cards current.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change `33` starter guides to `34` and “Thirty-three guides worth bookmarking.” to “Thirty-four guides worth bookmarking.”

**Step 2: Add the guide list item**

Append a new list item after the AI pilot exit criteria guide:

```html
<li>
  <div>
    <h3><a href="guides/ai-renewal-decision-checklist.html">AI renewal decision checklist</a></h3>
    <p>A practical review for deciding whether an AI contract should renew, renegotiate, narrow, pause, or end after real-world use.</p>
  </div>
</li>
```

**Step 3: Update next guides**

Replace the now-shipped next-topic card with a future useful topic, such as “AI policy meeting agenda” plus “AI sunset plan starter.”

---

### Task 5: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-08-10-ai-renewal-decision-checklist.md`

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
git add docs/plans/2026-08-10-ai-renewal-decision-checklist.md assets/ai-renewal-decision-checklist.svg guides/ai-renewal-decision-checklist.html index.html JOURNAL/2026-08-10-ai-renewal-decision-checklist.md
git commit -m "feat: add AI renewal decision checklist"
git push origin main
```
