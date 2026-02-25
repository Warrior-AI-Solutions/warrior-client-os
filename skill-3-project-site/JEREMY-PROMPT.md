# Jeremy — Project Site Generation Prompt

> Copy this prompt entirely. Attach the OMI transcript. Send to Jeremy.
> Output: complete VitePress site files, ready to push and deploy.

---

## THE PROMPT

---

Jeremy — Project Site Generation

Attached is an OMI transcript from a Warrior AI Solutions Project Discovery Session.

**Your job:** Extract all project data from this transcript and generate a complete VitePress project site following the Warrior AI Solutions design system.

---

### STEP 1 — Orient in the transcript

Use verbal section anchors to navigate:

- **Session header:** *"This is a Warrior AI Solutions Project Discovery Session for [CLIENT], project [NAME]"* → gives you project identity
- **Section anchors:** *"We are now in Section [N]: [Name]"* → marks each of the 8 data domains
- **Closing anchor:** *"End of session"* → marks transcript completion

If anchors are missing or unclear: infer section boundaries from topic shifts. Note which sections had poor coverage — flag these as **⚠️ OPEN ITEM** on the site. Do NOT fabricate content.

---

### STEP 2 — Extract the 8 data domains

| Domain | What to extract |
|--------|----------------|
| **D1 Project Identity** | Official name, working title, one-sentence problem statement, end user description, anti-vision (what it must NOT be) |
| **D2 Team & Roles** | Full name + role for every person mentioned |
| **D3 Architecture** | Every technical layer — frontend type, backend type, AI/ML components, data stores, infrastructure, integrations. Reconstruct the data flow from the step-by-step walkthrough |
| **D4 Work Breakdown** | Every milestone or phase mentioned. Use client's own language for names. Estimate from context if given. Classify as SP# (backend/infra work) or M# (frontend/feature work) |
| **D5 Current Status** | What is already done, what is being built now, what is coming next |
| **D6 Success Criteria** | Every number mentioned: users, response times, uptime, completion rates. Quote verbatim |
| **D7 Glossary** | Every project-specific term, acronym, or methodology label. Define each in plain language for non-technical readers |
| **D8 Resources** | Every URL, tool name, board link, repo reference mentioned |

---

### STEP 3 — Flag gaps honestly

For any domain with insufficient transcript coverage, add a clearly marked **⚠️ OPEN ITEM** placeholder on the relevant site page.

**Do NOT invent content. A site with honest gaps is better than a site with hallucinated data.**

Format for open items:
```
⚠️ OPEN ITEM: [Section] — [What is missing] — [Who should clarify this]
```

---

### STEP 4 — Generate the site

Build these files:

**Config:**
- `docs/.vitepress/config.mts` — title from D1, nav (Progress → Jira → Architecture → Security → QA), dark mode, Google Fonts
- `docs/.vitepress/theme/index.ts` — register all page components
- `docs/.vitepress/theme/custom.css` — copy from warrior-ai-web verbatim (CSS vars are universal)
- `package.json` — VitePress + Vue, bun runtime

**Pages (one .vue component + one .md entry each):**
- `HomePage.vue` / `index.md` — hero (D1), team badges (D2), live status strip (D5)
- `ProgressPage.vue` / `progress.md` — sprint/milestone cards (D4), status badges (D5), V0 gate (D6)
- `ArchitecturePage.vue` / `architecture.md` — layer diagram (D3), data flow, hosting
- `SecurityPage.vue` / `security.md` — security posture (D3-security), compliance, auth model, open items
- `QaPage.vue` / `qa.md` — success criteria (D6), metrics, sign-off conditions
- `JiraPage.vue` / `jira.md` — full ticket reference (D4, D8), board links

---

### STEP 5 — Design rules (non-negotiable)

```css
/* Colors */
--wai-navy-deep:    #0A1628;   /* page background */
--wai-navy-primary: #111827;   /* card backgrounds */
--wai-navy-light:   #1B2A4A;   /* borders */
--wai-gold:         #C8A84E;   /* primary accent */
--wai-text-primary: #F5F0E8;   /* headings */
--wai-text-muted:   #9CA3AF;   /* body text */

/* Status colors */
--status-done:    #059669;   /* green  — completed */
--status-active:  #C8A84E;   /* gold   — in progress */
--status-next:    #3B82F6;   /* blue   — coming next */
--status-backlog: #6B7280;   /* gray   — not started */

/* Mode */
appearance: 'dark'   /* dark mode only, always */
```

All pages use the `.wai-page` wrapper class.
No client logos or images in first version — text and color only.
Status pills use the four colors above consistently throughout.

---

### STEP 6 — Output format

Provide all files as clearly labeled code blocks:

```
=== docs/.vitepress/config.mts ===
[file contents]

=== docs/.vitepress/theme/custom.css ===
[file contents]

=== docs/.vitepress/theme/index.ts ===
[file contents]

=== docs/.vitepress/theme/HomePage.vue ===
[file contents]

... and so on for every file
```

Also include a `SETUP.md` with:
```bash
# 1. Install dependencies
bun install

# 2. Preview locally
bun run dev

# 3. Build for production
bun run build

# 4. Deploy (via GitHub push → Cloudflare Pages)
git add -A && git commit -m "feat: initial project site from discovery session" && git push
```

---

### STEP 7 — Summary for Steffen

After all the code, write a brief summary:

**Coverage:**
- D1 Project Identity: [good / partial / missing]
- D2 Team & Roles: [good / partial / missing]
- D3 Architecture: [good / partial / missing]
- D4 Work Breakdown: [good / partial / missing]
- D5 Current Status: [good / partial / missing]
- D6 Success Criteria: [good / partial / missing]
- D7 Glossary: [good / partial / missing]
- D8 Resources: [good / partial / missing]

**Open Items requiring client follow-up:**
- [List each OPEN ITEM with the clarifying question]

**Recommended next action:**
- [What should Steffen do before making the site public]

---

*End of prompt.*

---

## Notes on Transcript Quality

**Good transcript signals:**
- Verbal section anchors present → clean extraction
- Numbers spoken out loud → become metric cards
- Client uses their own terminology → becomes glossary

**Degraded transcript signals:**
- No anchors → Jeremy infers from topic shifts, flags lower confidence
- Crosstalk / multiple speakers → Jeremy attributes to roles, not names
- Tangents → Jeremy focuses on the 8 domains, ignores off-topic discussion

**When to re-run the session:**
- Fewer than 4 of the 8 domains have usable content
- The architecture section was skipped or too vague to reconstruct
- No success criteria were mentioned at all

---

*v1.0 — 2026-02-25*
