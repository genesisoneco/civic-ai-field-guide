# AI Agent Guide Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Publish a plain-language, source-backed guide that explains what an AI agent is and how ordinary readers can judge agentic systems without hype or panic.

**Architecture:** Keep the site static and inspectable: one HTML guide, one local SVG diagram, one homepage link, and one journal entry. Use the existing page structure, inline CSS pattern, Article JSON-LD, internal links, and source trail style already used by the field guide.

**Tech Stack:** Static HTML, SVG, Python standard-library validation, Git/GitHub.

---

### Task 1: Add an implementation plan file

**Objective:** Record the exact implementation path before changing public content.

**Files:**
- Create: `docs/plans/2026-05-29-ai-agent-guide.md`

**Step 1: Write the plan**

Create this markdown file with the required header, sequential tasks, validation commands, and expected commit.

**Step 2: Verify the file exists**

Run: `test -f docs/plans/2026-05-29-ai-agent-guide.md`
Expected: exit code 0.

**Step 3: Commit later with the public guide**

Do not commit this task alone; include it in the guide ship so the repository has one coherent change.

### Task 2: Create the agent loop SVG

**Objective:** Add a lightweight, rights-safe visual that distinguishes goals, tools, memory/context, action, observation, and human limits.

**Files:**
- Create: `assets/ai-agent-loop.svg`
- Test: XML parse check for SVG files

**Step 1: Create the SVG**

Use an accessible SVG with `<title>`, `<desc>`, text labels, simple shapes, and no external images or fonts.

**Step 2: Run parse check**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-agent-loop.svg')\nprint('svg ok')\nPY`
Expected: `svg ok`.

### Task 3: Publish the AI agent guide

**Objective:** Add the new source-backed public guide page.

**Files:**
- Create: `guides/what-is-an-ai-agent.html`
- Test: HTML parse and link checks

**Step 1: Write source-backed content**

Include: short answer, diagram, what makes a system agentic, what does not count, risk checklist, practical questions, source trail, and disclaimer.

**Step 2: Add metadata**

Add title, description, semantic headings, JSON-LD Article schema, datePublished/dateModified `2026-05-29`, and image reference to `../assets/ai-agent-loop.svg`.

**Step 3: Check local references**

Run the repository local href/src checker after all files are added.
Expected: no missing local files.

### Task 4: Link the guide from the homepage

**Objective:** Make the new guide discoverable from the starter path.

**Files:**
- Modify: `index.html`

**Step 1: Add the new guide to Start here**

Insert `guides/what-is-an-ai-agent.html` after the AI system guide.

**Step 2: Update Next guides to build**

Remove “What is an AI agent?” from future guides and leave a next practical civic-use guide.

**Step 3: Verify homepage link**

Run local link check.
Expected: link target exists.

### Task 5: Add the journal entry

**Objective:** Record self-assessment, evidence, assumptions, corrections, learning, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-05-29-what-is-ai-agent.md`

**Step 1: Write the journal entry**

Include required sections: Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, Next move.

**Step 2: Ensure no private details appear**

Run a scan over changed files for tokens, credentials, emails, and absolute local paths.
Expected: no findings.

### Task 6: Validate, commit, and push

**Objective:** Ship the update safely.

**Files:**
- All changed files

**Step 1: Run whitespace validation**

Run: `git diff --check`
Expected: no output and exit code 0.

**Step 2: Run HTML/SVG/link validation**

Run a Python standard-library script that parses all HTML, parses SVG assets, and checks local `href`/`src` references.
Expected: all checks pass.

**Step 3: Run source reachability check**

Run HEAD/GET checks for cited source URLs.
Expected: HTTP 200 for each source URL.

**Step 4: Review diff and status**

Run: `git diff --stat && git status --short`
Expected: only intended files changed.

**Step 5: Commit**

```bash
git add index.html guides/what-is-an-ai-agent.html assets/ai-agent-loop.svg docs/plans/2026-05-29-ai-agent-guide.md JOURNAL/2026-05-29-what-is-ai-agent.md
git commit -m "feat: explain what an AI agent is"
```

**Step 6: Push**

Run: `git push origin main`
Expected: push succeeds. If rejected, fetch/rebase once, rerun validation, then push again.
