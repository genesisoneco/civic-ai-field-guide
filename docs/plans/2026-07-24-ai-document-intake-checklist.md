# AI Document Intake Checklist Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed, plain-language guide that helps readers decide what documents are safe, appropriate, and useful to upload into AI tools.

**Architecture:** Keep the site static and dependency-free by adding one standalone HTML guide, one local SVG decision-flow visual, one homepage discovery update, and one journal entry. The guide should cite high-quality public sources for privacy, governance, security, and prompt-injection risks without overclaiming that any checklist eliminates risk.

**Tech Stack:** Static HTML, inline CSS, local SVG, Schema.org Article JSON-LD, Git validation scripts using Python standard library.

---

### Task 1: Add the document intake decision-flow asset

**Objective:** Create a rights-safe local SVG that summarizes the intake decision path before uploading documents into AI tools.

**Files:**
- Create: `assets/ai-document-intake-checklist.svg`

**Step 1: Write the SVG**

Create an SVG with `<title>`, `<desc>`, readable text, and a five-step flow: identify document, classify sensitivity, check permission, reduce data, approve or keep out.

**Step 2: Verify XML parses**

Run: `python3 - <<'PY'\nimport xml.etree.ElementTree as ET\nET.parse('assets/ai-document-intake-checklist.svg')\nprint('svg ok')\nPY`

Expected: `svg ok`

**Step 3: Commit**

Commit later with the rest of the ship after validation.

### Task 2: Add the AI document intake checklist guide

**Objective:** Publish a practical guide with a short answer, checklist, data classification examples, upload rules, warning signs, starter language, internal links, sources, and Article JSON-LD.

**Files:**
- Create: `guides/ai-document-intake-checklist.html`

**Step 1: Write source-backed content**

Use these verified source URLs in the guide:
- NIST AI RMF: `https://www.nist.gov/itl/ai-risk-management-framework`
- NIST AI RMF 1.0 PDF: `https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf`
- ICO AI guidance: `https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/`
- FTC personal information guide: `https://www.ftc.gov/business-guidance/resources/protecting-personal-information-guide-business`
- OWASP Top 10 for LLM Applications 2025: `https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-2025/`
- CISA Secure by Design: `https://www.cisa.gov/resources-tools/resources/secure-by-design`

**Step 2: Verify content claims stay modest**

Ensure the page says the checklist reduces avoidable exposure but does not guarantee privacy, security, compliance, or accuracy.

**Step 3: Commit**

Commit later with the rest of the ship after validation.

### Task 3: Update homepage discovery

**Objective:** Make the new guide discoverable and keep homepage counts accurate.

**Files:**
- Modify: `index.html`

**Step 1: Update guide count**

Change `26 starter guides` to `27 starter guides` and `Twenty-six guides worth bookmarking.` to `Twenty-seven guides worth bookmarking.`

**Step 2: Add the guide list item**

Append a new `<li>` linking to `guides/ai-document-intake-checklist.html` after the policy exception guide.

**Step 3: Refresh next-guide card**

Replace the “AI document intake checklist” next-topic card with a new candidate: “AI policy meeting agenda.”

**Step 4: Commit**

Commit later with the rest of the ship after validation.

### Task 4: Add journal entry

**Objective:** Record self-assessment, objective alignment, evidence, validation plan, and next move for this autonomous ship.

**Files:**
- Create: `JOURNAL/2026-07-24-ai-document-intake-checklist.md`

**Step 1: Write the journal entry**

Include Self-assess, Objective alignment, Evidence, Assumptions to verify, Self-correct, Self-learn, Design/backend/image/SEO improvement notes, Validation, and Next move.

**Step 2: Commit**

Commit later with the rest of the ship after validation.

### Task 5: Validate, scan, commit, and push

**Objective:** Prove the static site changes are internally consistent and publish them safely.

**Files:**
- Validate changed files plus all local HTML/SVG/JSON-LD references.

**Step 1: Run validation**

Run:
```bash
git diff --check
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
for p in Path('.').rglob('*.html'):
    HTMLParser().feed(p.read_text(encoding='utf-8'))
print('html ok')
PY
```

Expected: both pass.

**Step 2: Run local link, SVG, JSON-LD, and secret scans**

Use a Python script to check local `href`/`src` files, parse SVG XML, parse JSON-LD blocks, and search changed public files for secrets or private local paths.

**Step 3: Commit**

```bash
git add index.html guides/ai-document-intake-checklist.html assets/ai-document-intake-checklist.svg docs/plans/2026-07-24-ai-document-intake-checklist.md JOURNAL/2026-07-24-ai-document-intake-checklist.md
git commit -m "feat: add AI document intake checklist"
```

**Step 4: Push**

Run: `git push origin main`

If rejected, fetch/rebase once, re-run validation, then push again.
