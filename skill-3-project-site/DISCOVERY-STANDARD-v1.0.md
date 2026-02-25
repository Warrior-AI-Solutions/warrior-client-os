# Skill 3 — Discovery Session Standard (v1.0)

> The structured discovery session that produces everything Jeremy needs to build the project site from a single OMI transcript.

---

## Overview

Every project site starts with one session — 2–4 hours, recorded by OMI. No forms. No prep. Just a structured conversation with a hidden skeleton.

Stakeholders experience a natural strategic discussion about their project.
We extract all 8 data domains needed to build the site.
Jeremy does the rest.

**The pipeline:**
```
Discovery Session (2–4h, OMI recording)
    → OMI transcript
        → Jeremy parses transcript (see JEREMY-PROMPT.md)
            → VitePress site files generated
                → Cloudflare Pages deploys
                    → Stakeholders get a URL
```

---

## The 8 Data Domains

Everything on the project site maps to one of these. Every question in the session feeds one.

| # | Domain | What It Captures | Site Section |
|---|--------|-----------------|--------------|
| D1 | **Project Identity** | Name, tagline, problem, audience | Hero + Overview |
| D2 | **Team & Roles** | Who's building, who's the client, stakeholders | Team section |
| D3 | **Architecture** | Frontend, Backend, AI, Infra, Security layers | Architecture page |
| D4 | **Work Breakdown** | Sprints / Milestones: names, descriptions, estimates | Progress page |
| D5 | **Current Status** | Done, active, next | Status badges + metrics strip |
| D6 | **Success Criteria** | Metrics, thresholds, gate conditions, sign-off | QA / V0 gate |
| D7 | **Glossary** | Project-specific terms for non-technical readers | Glossary section |
| D8 | **Resources** | Jira, repos, external tools, dashboards | Resources / Jira page |

---

## Before the Session

**Facilitator (Steffen) prepares:**
- OMI device charged and connected
- Recording started BEFORE anyone enters the room
- Nothing else. No slides, no forms, no prep docs for the client.

**Opening statement — say this out loud:**
> *"This is a Warrior AI Solutions Project Discovery Session for [CLIENT NAME], project [PROJECT NAME]. Today's date is [DATE]. Present are: [NAME and ROLE for each person]. We are beginning Section 1."*

This verbal header is how Jeremy orients in the transcript. It must happen.

---

## The 8 Sections

---

### SECTION 1 — Project Identity (15–25 min)
**Verbal anchor:** *"We are now in Section 1: Project Identity."*

**Goal:** Capture D1 — the name, the problem, the vision, the audience.

**Questions:**
1. What is the official name of this project? Is there a working title?
2. In one sentence — what problem does this solve? Who has that problem today?
3. Who is the end user? Paint me a picture — what do they do, what do they struggle with, what do they want?
4. What does "wild success" look like in 12 months? If this works perfectly, what changes?
5. What's the one thing this project must absolutely NOT be? *(Anti-vision — forces clarity)*
6. Is there a name for the methodology or framework this serves? *(e.g., "Core 4", "our sales process", "the XYZ method")* — these become glossary entries.

**Listen for:** Any specific language the client uses to describe their world. Quote it exactly. These words go in the glossary.

---

### SECTION 2 — Scope & Boundaries (20–30 min)
**Verbal anchor:** *"We are now in Section 2: Scope and Boundaries."*

**Goal:** Capture D4 (work breakdown) and define what's IN and OUT of scope.

**Questions:**
1. What are we actually building? List every major piece — nothing is too small.
2. For each piece: is this new, or are we integrating with / modifying something existing?
3. What is explicitly OUT of scope for this engagement?
4. If we had to cut 30% of scope to hit the deadline — what goes first? *(Reveals priorities)*
5. Are there external systems, platforms, or vendors this depends on that we don't control?
6. Are there compliance, legal, or regulatory requirements? *(GDPR, data residency, industry certifications)*

**Listen for:** Natural groupings — clients cluster features without realizing it. Those clusters become milestones (M1, M2…) or sprint packages (SP1, SP2…).

---

### SECTION 3 — Technical Architecture (30–45 min)
**Verbal anchor:** *"We are now in Section 3: Technical Architecture."*

**Goal:** Capture D3 — every layer of the system.

**Questions:**
1. What does the user touch? *(Frontend — app, web portal, widget, extension?)*
2. Where does the data live? *(Database — cloud, self-hosted, existing system?)*
3. What's the brain of the system? *(Backend — API, workflow engine, AI model, automation?)*
4. Are there AI or ML components? If yes: what model, what provider, what data does it need?
5. Walk me through a user doing the most important thing in the system — step by step.
6. What already exists that we're building on top of or integrating with?
7. Where is this hosted? Who controls the infrastructure?
8. Are there existing APIs, webhooks, or data feeds involved?

**Facilitator note:** Draw the architecture as they describe it. At the end, read it back:
> *"So what I'm hearing is: the user opens [X], it talks to [Y], which talks to [Z], and the result comes back as [W]. Is that right?"*

This confirmation ends up in the transcript and Jeremy uses it as the canonical data flow description.

---

### SECTION 4 — Team & Roles (10–15 min)
**Verbal anchor:** *"We are now in Section 4: Team and Roles."*

**Goal:** Capture D2 — who is who.

**Questions:**
1. Who are the people in this room, and what is each person's role?
2. Who is the final decision-maker on scope and priorities?
3. Who is the primary technical contact on the client side?
4. Who are the end users — and is any of them in this room?
5. On the Warrior AI side: who is leading the build, and who is the client's main point of contact?
6. Are there external partners, agencies, or contractors involved?

**Capture:** Full name + role for each person. These go directly into the site's team section.

---

### SECTION 5 — Timeline & Milestones (20–30 min)
**Verbal anchor:** *"We are now in Section 5: Timeline and Milestones."*

**Goal:** Capture D4 (milestones with estimates) and D5 (current status).

**Questions:**
1. Is there a hard deadline? A launch event, a contract date, a market window?
2. What needs to be true by that deadline — what is the minimum viable version?
3. Working backwards — what are the natural phases of this project?
4. For each phase: what does it produce? What can someone see or test at the end?
5. Are there phases that can run in parallel?
6. What is the very first thing we will build — what can we show in Week 1?
7. On a scale of 1–10, how much does the timeline flex? *(1 = hard deadline, 10 = ship when it's right)*

**Listen for:** Clients often name their milestones organically — *"the MVP"*, *"the pilot"*, *"the full rollout"*. Use their language exactly on the site.

---

### SECTION 6 — Success Criteria (15–20 min)
**Verbal anchor:** *"We are now in Section 6: Success Criteria."*

**Goal:** Capture D6 — measurable definition of done.

**Questions:**
1. How will we know this project is successful? Not "it's live" — what *measurable* outcome proves it?
2. Are there specific performance thresholds? *(Load time, response time, uptime, concurrent users)*
3. Are there user adoption metrics? *(How many users, what completion rate, what engagement threshold)*
4. Who signs off on each milestone? What does sign-off look like?
5. What would make you say *"this failed"* — even if it shipped?
6. Is there a pilot or alpha phase with a small group before full rollout?

**Listen for:** Numbers. Every number becomes a metric card on the site.
*"We need 500 users"* → metric card. *"Response under 2 seconds"* → metric card. Quote exact numbers verbatim.

---

### SECTION 7 — Security & Compliance (10–15 min)
**Verbal anchor:** *"We are now in Section 7: Security and Compliance."*

**Goal:** Capture D3-security — feeds the Security page.

**Questions:**
1. What data will this system handle? Is any of it sensitive? *(personal, health, financial, credentials)*
2. Are there regulatory requirements? *(GDPR, HIPAA, SOC2, PCI-DSS, industry-specific)*
3. Who can access what? Are there user roles or permission levels?
4. Where does authentication happen? Existing auth system or do we build one?
5. Are there known risks or concerns from the client's side?
6. Who is responsible for ongoing security monitoring after launch?

**Note:** If the answer is "we don't know yet" — that goes in the transcript. Unknowns become ⚠️ OPEN ITEMs on the site.

---

### SECTION 8 — Resources & Ecosystem (10–15 min)
**Verbal anchor:** *"We are now in Section 8: Resources and Ecosystem."*

**Goal:** Capture D8 — links, tools, boards, external systems.

**Questions:**
1. Is there an existing Jira / Linear / Notion project? What's the URL?
2. Where will the code live? GitHub org, GitLab, existing repo?
3. What tools does the client's team use that we need to connect with or respect?
4. Are there existing design files, brand guides, or style references?
5. Is there an existing website or product page for the client's brand?
6. Who else needs access to this project site when it goes live?

---

### CLOSING (5 min)
**Verbal anchor:** *"We are now in the Closing section."*

**Facilitator says:**
> *"Before we close: is there anything critical to this project that we haven't discussed? Any constraint, dependency, or context that would change what we build or how we build it?"*

Then:
> *"This session is complete. Recorded for [CLIENT NAME], project [PROJECT NAME], [DATE]. End of session."*

The closing anchor tells Jeremy the transcript is complete and extraction can begin.

---

## Repeatable Checklist

**Day of discovery session:**
- [ ] OMI charged and recording before people enter
- [ ] Verbal session header spoken (client name, project name, date, attendees)
- [ ] All 8 sections completed with verbal anchors
- [ ] Verbal closing spoken
- [ ] OMI transcript exported immediately after session

**Same day / next morning:**
- [ ] Paste JEREMY-PROMPT.md + transcript into Jeremy
- [ ] Review OPEN ITEMS list
- [ ] Jeremy generates site files
- [ ] Create new repo: `warrior-ai-solutions/[project-slug]-site`
- [ ] Connect to Cloudflare Pages (auto-deploy on push)
- [ ] Send URL to all stakeholders

**Within 48 hours:**
- [ ] Fill in OPEN ITEMS with client follow-up
- [ ] Add Jira board link once project is created
- [ ] Share site URL in project Slack/email thread

---

*Warrior AI Solutions — Project Site Standard v1.0*
*Created: 2026-02-25*
