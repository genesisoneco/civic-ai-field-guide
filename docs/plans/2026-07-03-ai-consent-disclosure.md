# AI Consent and Disclosure Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Add a source-backed field guide page that helps schools, workplaces, public offices, and community groups decide when to disclose AI involvement and what meaningful consent or refusal paths should include.

**Architecture:** Keep the project static and lightweight: one HTML guide, one local rights-safe SVG, one homepage index update, and one journal entry. Follow the existing guide pattern with inline CSS, Article JSON-LD, semantic sections, source list, print styles, and internal links.

**Tech Stack:** Static HTML5, inline CSS, SVG, Schema.org JSON-LD, Python standard-library validation scripts, Git/GitHub.

---

### Task 1: Add the AI consent and disclosure guide

**Objective:** Create a practical, cited guide page with clear disclosure templates and consent checks.

**Files:**
- Create: `guides/ai-consent-disclosure.html`
- Later linked from: `index.html`

**Step 1: Write the content scaffold**

Create `guides/ai-consent-disclosure.html` with:
- `<title>AI Consent and Disclosure | Civic AI Field Guide</title>`
- Meta description about telling people when AI is involved and when consent or refusal matters.
- Article JSON-LD with `datePublished` and `dateModified` set to `2026-07-03`.
- Sections: short answer, why disclosure matters, disclosure vs consent, when notice is enough, when opt-out/refusal should exist, when explicit consent is needed, disclosure templates, consent checklist, sources.

**Step 2: Add source-backed claims only**

Use these sources in the source list and avoid unsupported legal claims:
- NIST AI Risk Management Framework: `https://www.nist.gov/itl/ai-risk-management-framework`
- NIST AI RMF 1.0 publication: `https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10`
- White House Blueprint for an AI Bill of Rights archive: `https://bidenwhitehouse.archives.gov/ostp/ai-bill-of-rights/`
- UNESCO guidance for generative AI in education and research: `https://unesdoc.unesco.org/ark:/48223/pf0000386693`
- European Commission AI Act overview: `https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai`

**Step 3: Include complete user-facing templates**

Add copy-paste templates for:
- AI assisted draft.
- AI supported decision, human review available.
- Optional AI feature.
- AI chatbot or automated help.
- High-stakes no-consent warning.

**Step 4: Verify page structure**

Run: `python3 - <<'PY' ... HTMLParser check ... PY`
Expected: the new HTML file parses without parser exceptions.

**Step 5: Commit later with all files**

Do not commit until tasks 2-5 are complete.

---

### Task 2: Add a local explanatory SVG

**Objective:** Add a rights-safe visual that explains a simple notice-to-consent decision ladder.

**Files:**
- Create: `assets/ai-consent-disclosure.svg`
- Modify: `guides/ai-consent-disclosure.html`

**Step 1: Create the SVG**

Create an SVG with:
- `<title>AI notice and consent ladder</title>`
- `<desc>` explaining the ladder.
- Five steps: name the AI use, explain the purpose, show stakes, offer choice/review, record feedback.
- No external images, fonts, or rights-restricted assets.

**Step 2: Reference it from the guide**

Add:
```html
<figure>
  <img src="../assets/ai-consent-disclosure.svg" alt="A five-step AI notice and consent ladder: name the AI use, explain the purpose, show the stakes, offer choice or review, and record feedback.">
  <figcaption>...</figcaption>
</figure>
```

**Step 3: Verify SVG XML**

Run: `python3 - <<'PY' ... xml.etree.ElementTree.parse('assets/ai-consent-disclosure.svg') ... PY`
Expected: parse succeeds.

---

### Task 3: Update the homepage guide list

**Objective:** Make the new guide discoverable from the homepage and update guide count.

**Files:**
- Modify: `index.html`

**Step 1: Update count text**

Change:
- `17` starter guides to `18` starter guides.
- `Seventeen guides worth bookmarking.` to `Eighteen guides worth bookmarking.`

**Step 2: Add list item**

After the AI translation guide, add:
```html
<li>
  <div>
    <h3><a href="guides/ai-consent-disclosure.html">AI consent and disclosure</a></h3>
    <p>A plain-language guide to telling people when AI is involved, when consent matters, and what review or refusal paths should exist.</p>
  </div>
</li>
```

**Step 3: Refresh next-topic cards**

Replace the existing AI consent card with a new future topic, such as AI policy meeting agenda or AI audit trail basics, so the page does not advertise already-published work as upcoming.

---

### Task 4: Add the journal entry

**Objective:** Record self-assessment, evidence, validation, and next move for this autonomous ship.

**Files:**
- Create: `JOURNAL/2026-07-03-ai-consent-disclosure.md`

**Step 1: Include required sections**

Use headings:
- Self-assess
- Objective alignment
- Evidence
- Assumptions to verify
- Self-correct
- Self-learn
- Design/backend/image/SEO improvement notes
- Validation
- Next move

**Step 2: Record validation honestly**

List source URL status checks, parser checks, internal link checks, diff check, secret scan, and note that no full build command exists if that remains true.

---

### Task 5: Validate, scan, commit, and push

**Objective:** Ensure the static site is internally consistent and publish the change.

**Files:**
- All changed files.

**Step 1: Run validation**

Run:
```bash
git diff --check
python3 - <<'PY'
# parse all HTML, SVG, JSON-LD, and local href/src references
PY
```
Expected: no errors.

**Step 2: Scan changed files for private info**

Run a local scan over `git diff --cached` or changed files for token-like strings, local private paths, emails, and credentials. Expected: no secrets or private operator details.

**Step 3: Commit**

```bash
git add guides/ai-consent-disclosure.html assets/ai-consent-disclosure.svg index.html docs/plans/2026-07-03-ai-consent-disclosure.md JOURNAL/2026-07-03-ai-consent-disclosure.md
git commit -m "feat: add AI consent disclosure guide"
```

**Step 4: Push safely**

```bash
git push origin main
```

If rejected, run `git fetch origin main`, `git rebase origin/main`, rerun validation, then push once more. If conflicts or new validation errors occur, stop and report the full error text.
