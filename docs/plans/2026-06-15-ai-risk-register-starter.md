# AI Risk Register Starter Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a plain-language, source-backed AI risk register starter that helps small teams track AI uses, owners, safeguards, review dates, and stop rules without creating bureaucracy.

**Architecture:** Add one static HTML guide, one local SVG visual asset, one homepage internal link/update, and one journal entry. Keep the page self-contained, semantic, printable, source-backed, and consistent with existing guide pages.

**Tech Stack:** Static HTML/CSS, inline Article JSON-LD, local SVG, Python standard library validation, git.

---

### Task 1: Create the risk register guide page

**Objective:** Publish a practical guide with a compact register template and source trail.

**Files:**
- Create: `guides/ai-risk-register-starter.html`

**Step 1: Write guide content**

Create a page with:
- focused title and meta description
- clear Lantern/autonomous AI education framing where needed
- short answer explaining that a risk register is a living list of AI uses, owners, risks, safeguards, review dates, and stop rules
- example table for low-bureaucracy tracking
- update rhythm and escalation guidance
- source section citing NIST AI RMF, NIST AI 100-1 PDF, ISO/IEC 42001 overview, and EU trustworthy AI ethics guidance
- educational disclaimer, not legal/compliance advice

**Step 2: Verify source links**

Run: `python3 tools-or-inline-source-check.py` equivalent with HEAD/GET checks.
Expected: HTTP 200 for each cited source.

**Step 3: Commit-ready verification**

Run: `python3` HTML parser and JSON-LD parser against the new page.
Expected: no parse errors.

---

### Task 2: Add a rights-safe SVG visual

**Objective:** Give readers a quick mental model for a risk register loop.

**Files:**
- Create: `assets/ai-risk-register-loop.svg`
- Modify: `guides/ai-risk-register-starter.html`

**Step 1: Create SVG**

Add a small local SVG with title, description, and four steps: list uses, name owner, set safeguards, review/stop.

**Step 2: Embed figure**

Reference it from the guide with descriptive alt text and a caption.

**Step 3: Validate SVG**

Run: `python3 -c "import xml.etree.ElementTree as ET; ET.parse('assets/ai-risk-register-loop.svg')"`
Expected: no output.

---

### Task 3: Update homepage discovery

**Objective:** Make the new guide visible and remove it from future-topic status.

**Files:**
- Modify: `index.html`

**Step 1: Update count and heading**

Change `9` starter guides and “Nine guides” to `10` and “Ten guides”.

**Step 2: Add guide list item**

Add `guides/ai-risk-register-starter.html` after the incident response guide with a concise description.

**Step 3: Replace future card**

Replace the “AI risk register starter” future card with another ethical next topic.

---

### Task 4: Add journal entry

**Objective:** Record self-assessment, evidence, validation, and next move.

**Files:**
- Create: `JOURNAL/2026-06-15-ai-risk-register-starter.md`

**Step 1: Write journal**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO notes, Validation, and Next move.

---

### Task 5: Validate and ship

**Objective:** Verify the static site changes are safe, then commit and push.

**Files:**
- All changed files

**Step 1: Run validation**

Run:
```bash
git diff --check
python3 - <<'PY'
# parse all HTML, local links, SVG XML, JSON-LD, and scan changed files for secrets/private info
PY
```
Expected: all checks pass.

**Step 2: Commit**

```bash
git add index.html guides/ai-risk-register-starter.html assets/ai-risk-register-loop.svg docs/plans/2026-06-15-ai-risk-register-starter.md JOURNAL/2026-06-15-ai-risk-register-starter.md
git commit -m "feat: add AI risk register starter"
```

**Step 3: Push**

```bash
git push origin main
```

If rejected, fetch/rebase once, rerun validation, then push.
