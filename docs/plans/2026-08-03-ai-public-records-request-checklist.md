# AI Public Records Request Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language checklist for reviewing AI-assisted public-records search, summaries, redaction notes, and response drafts before they affect requesters or disclosure logs.

**Architecture:** Keep the site static and copy the established guide pattern: one standalone HTML guide, one local SVG visual, one homepage discovery update, and one journal entry. Avoid legal advice; cite public, high-quality sources and keep practical steps focused on verification, records, privacy, redaction, appeal paths, and accountable human review.

**Tech Stack:** Static HTML, inline CSS, local SVG, JSON-LD Article metadata, Python standard-library validation scripts, GitHub Pages.

---

### Task 1: Create the implementation plan

**Objective:** Document the intended change before editing public content.

**Files:**
- Create: `docs/plans/2026-08-03-ai-public-records-request-checklist.md`

**Step 1: Write this plan**

Create this Markdown file with goal, architecture, task list, source plan, validation plan, and commit instructions.

**Step 2: Verify the file exists**

Run: `test -f docs/plans/2026-08-03-ai-public-records-request-checklist.md`
Expected: exit code 0.

**Step 3: Commit later with the full ship**

Do not commit yet; include this file with the guide, asset, homepage update, and journal.

---

### Task 2: Create the SVG review-flow visual

**Objective:** Add a rights-safe visual that makes the public-records review loop easier to scan.

**Files:**
- Create: `assets/ai-public-records-request-checklist.svg`

**Step 1: Write the SVG**

Use a local SVG with `<title>` and `<desc>`, five labeled gates, high contrast, and no external dependencies.

**Step 2: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-public-records-request-checklist.svg')\nprint('ok')\nPY`
Expected: `ok`.

---

### Task 3: Add the public-records checklist guide

**Objective:** Publish a practical guide for AI-assisted records workflows without overstating legal certainty.

**Files:**
- Create: `guides/ai-public-records-request-checklist.html`

**Step 1: Add a standalone guide page**

Include:
- title and meta description
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-08-03`
- short answer
- SVG figure with descriptive alt text and caption
- source-backed explanation of why review matters
- minimum checks table
- risky AI uses grid
- workflow checklist
- redaction and summary cautions
- lightweight review log
- stop rules
- requester-facing starter language
- related internal links
- sources and disclaimer

**Step 2: Use these sources**

Cite only public source URLs checked during the run:
- `https://www.foia.gov/how-to.html`
- `https://www.justice.gov/oip/doj-guide-freedom-information-act-0`
- `https://www.archives.gov/records-mgmt/rcs`
- `https://www.nist.gov/itl/ai-risk-management-framework`
- `https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf`

**Step 3: Verify HTML parses**

Run the repository HTML parser check after all edits.
Expected: all HTML files parse without parser errors.

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable from the homepage.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change `30` starter guides to `31` and “Thirty guides worth bookmarking.” to “Thirty-one guides worth bookmarking.”

**Step 2: Add the guide list item**

Append a new list item after the AI grant application checklist:

```html
<li>
  <div>
    <h3><a href="guides/ai-public-records-request-checklist.html">AI public records request checklist</a></h3>
    <p>A practical review for AI-assisted search, summaries, redaction notes, and response drafts before public-records work reaches requesters.</p>
  </div>
</li>
```

**Step 3: Update next guides**

Replace the now-shipped next-topic card with a future useful topic, such as “AI policy meeting agenda”.

---

### Task 5: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, and next move for the autonomous run.

**Files:**
- Create: `JOURNAL/2026-08-03-ai-public-records-request-checklist.md`

**Step 1: Include required sections**

Add: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Name source checks and validation**

Record source reachability, parser checks, link checks, SVG checks, JSON-LD checks, diff check, and secret scan.

---

### Task 6: Validate, scan, commit, and push

**Objective:** Verify the static site and publish the ship safely.

**Files:**
- All changed files

**Step 1: Run validation**

Run:

```bash
git diff --check
python3 tools_or_inline_html_check.py
python3 tools_or_inline_link_check.py
python3 tools_or_inline_svg_check.py
python3 tools_or_inline_jsonld_check.py
```

Expected: all checks pass. If no full site build tool exists, state that in the journal.

**Step 2: Scan changed files for private information**

Run a local scan for tokens, credential patterns, private paths, emails, and secrets in changed files. Expected: no findings requiring changes.

**Step 3: Commit**

```bash
git add index.html guides/ai-public-records-request-checklist.html assets/ai-public-records-request-checklist.svg docs/plans/2026-08-03-ai-public-records-request-checklist.md JOURNAL/2026-08-03-ai-public-records-request-checklist.md
git commit -m "feat: add AI public records request checklist"
```

**Step 4: Push**

```bash
git push origin main
```

If rejected, fetch and rebase once, rerun validation, then push again. Do not force-push.
