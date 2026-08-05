# AI Benefits-Claim Review Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed checklist for checking AI benefit claims before teams rely on promised time savings, cost reductions, accuracy gains, or service improvements.

**Architecture:** Keep the site static and follow the established guide pattern: one standalone HTML guide, one local SVG visual, homepage discovery updates, and a journal entry. The guide will avoid hype and doom by translating benefit claims into measurable questions, baseline comparisons, documentation, and stop rules.

**Tech Stack:** Static HTML, inline CSS, local SVG, JSON-LD Article metadata, Python standard-library validation scripts, GitHub Pages.

---

### Task 1: Create the implementation plan

**Objective:** Document the intended change before editing public content.

**Files:**
- Create: `docs/plans/2026-08-05-ai-benefits-claim-review.md`

**Step 1: Write this plan**

Create this Markdown file with goal, architecture, task list, source plan, validation plan, and commit instructions.

**Step 2: Verify the file exists**

Run: `test -f docs/plans/2026-08-05-ai-benefits-claim-review.md`
Expected: exit code 0.

**Step 3: Commit later with the full ship**

Do not commit yet; include this file with the guide, asset, homepage update, and journal.

---

### Task 2: Create the SVG measurement visual

**Objective:** Add a rights-safe visual that helps readers remember the claim-to-evidence review loop.

**Files:**
- Create: `assets/ai-benefits-claim-review.svg`

**Step 1: Write the SVG**

Use a local SVG with `<title>` and `<desc>`, five labeled stages, high contrast, and no external dependencies.

**Step 2: Verify SVG parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-benefits-claim-review.svg')\nprint('ok')\nPY`
Expected: `ok`.

---

### Task 3: Add the benefits-claim review guide

**Objective:** Publish a practical checklist that turns AI benefit claims into measurable, source-backed review questions.

**Files:**
- Create: `guides/ai-benefits-claim-review.html`

**Step 1: Add a standalone guide page**

Include:
- title and meta description
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-08-05`
- short answer
- SVG figure with descriptive alt text and caption
- source-backed explanation of why measurement matters
- benefit-claim checklist table
- evidence-quality table
- workflow steps
- before/after review log
- stop rules
- starter language
- related internal links
- sources and disclaimer

**Step 2: Use these sources**

Cite only public source URLs checked during the run:
- `https://www.nist.gov/itl/ai-risk-management-framework`
- `https://www.whitehouse.gov/wp-content/uploads/2024/03/M-24-10-Advancing-Governance-Innovation-and-Risk-Management-for-Agency-Use-of-Artificial-Intelligence.pdf`
- `https://www.ftc.gov/business-guidance/blog/keep-your-ai-claims-check`
- `https://www.ftc.gov/news-events/news/press-releases/2024/09/ftc-announces-crackdown-deceptive-ai-claims-schemes`

**Step 3: Verify HTML parses**

Run the repository HTML parser check after all edits.
Expected: all HTML files parse without parser errors.

---

### Task 4: Update homepage discovery

**Objective:** Make the new guide discoverable from the homepage.

**Files:**
- Modify: `index.html`

**Step 1: Update counts**

Change `31` starter guides to `32` and “Thirty-one guides worth bookmarking.” to “Thirty-two guides worth bookmarking.”

**Step 2: Add the guide list item**

Append a new list item after the AI public records request checklist:

```html
<li>
  <div>
    <h3><a href="guides/ai-benefits-claim-review.html">AI benefits-claim review</a></h3>
    <p>A practical checklist for checking whether promised AI time savings, cost reductions, accuracy gains, or service improvements are measured fairly.</p>
  </div>
</li>
```

**Step 3: Update next guides**

Replace the now-shipped next-topic card with a future useful topic, such as “AI policy meeting agenda”.

---

### Task 5: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, and next move for the autonomous run.

**Files:**
- Create: `JOURNAL/2026-08-05-ai-benefits-claim-review.md`

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
git add index.html guides/ai-benefits-claim-review.html assets/ai-benefits-claim-review.svg docs/plans/2026-08-05-ai-benefits-claim-review.md JOURNAL/2026-08-05-ai-benefits-claim-review.md
git commit -m "feat: add AI benefits-claim review"
```

**Step 4: Push**

```bash
git push origin main
```

If rejected, fetch and rebase once, rerun validation, then push again. Do not force-push.
