# Warrior AI Solutions — Client OS

> **"From Discovery to Six Figures."**
> The complete system for acquiring, scoping, and delivering AI implementation projects at premium prices.

---

## What Is This?

This repository is the living standard for how Warrior AI Solutions runs every client engagement — from first conversation to deployed product.

It contains three skills that form a complete pipeline. Each client project flows through all three. The output is a live stakeholder website, a signed contract, and a delivered product.

**This is not a template library. This is an operating system.**

---

## The Three-Skill Pipeline

```
COMPANY PROBLEM
      │
      ▼
┌─────────────────────────────────┐
│  SKILL 1 — Product Discovery    │
│  "What should we build?"        │
│                                 │
│  Input:  Company struggles,     │
│          processes, pain points │
│  Output: Product brief —        │
│          avatar, jobs-to-be-    │
│          done, market sizing,   │
│          ROI projection,        │
│          value proposition      │
└─────────────────────────────────┘
      │
      ▼
┌─────────────────────────────────┐
│  SKILL 2 — Tech Scoping         │
│  "How do we build it?"          │
│                                 │
│  Input:  Product brief          │
│  Output: Architecture layers,   │
│          sprint breakdown,      │
│          stack decisions,       │
│          effort estimates,      │
│          team structure         │
└─────────────────────────────────┘
      │
      ▼
┌─────────────────────────────────┐
│  SKILL 3 — Project Site         │
│  "Show it. Sell it. Ship it."   │
│                                 │
│  Input:  OMI transcript from    │
│          discovery sessions     │
│  Output: Live VitePress site —  │
│          proposal, docs, QA,    │
│          coordination hub,      │
│          pricing & offer page   │
└─────────────────────────────────┘
      │
      ▼
SIGNED CONTRACT + DELIVERED PRODUCT
```

---

## The Five Audiences the Site Serves

| Audience | What They Need |
|----------|---------------|
| **Client executives** | Vision, ROI, investment summary — *"what am I buying?"* |
| **Client technical team** | Architecture, API contracts, security posture |
| **QA / testers** | Success criteria, metrics, sign-off conditions |
| **Coding partners** | Sprint breakdown, tickets, technical specs |
| **Decision-makers (new)** | The offer — scope, timeline, pricing, monthly ops cost |

The site IS the proposal. It's live before the contract is signed. It updates as the project evolves. It never goes stale.

---

## Repository Structure

```
warrior-client-os/
│
├── README.md                         ← You are here
├── CLIENT-OS.md                      ← Full system overview
│
├── skill-1-product-discovery/        ← Skill 1: Identify the product
│   ├── README.md
│   └── sessions/                     ← Sparring + discovery outputs
│
├── skill-2-tech-scoping/             ← Skill 2: Technical planning
│   ├── README.md
│   └── sessions/
│
├── skill-3-project-site/             ← Skill 3: Stakeholder site
│   ├── README.md
│   ├── DISCOVERY-STANDARD-v1.0.md   ← Full session agenda + structure
│   ├── JEREMY-PROMPT.md             ← AI prompt: transcript → site
│   └── site-template/               ← VitePress starter (coming)
│
└── sparring/                         ← First Principles + Red Team outputs
```

---

## Current Status

| Skill | Status | Notes |
|-------|--------|-------|
| Skill 1 — Product Discovery | 🟡 Spec in progress | Vision defined, needs full session design |
| Skill 2 — Tech Scoping | 🟡 Spec in progress | Vision defined, needs full session design |
| Skill 3 — Project Site | 🟢 v1.0 Draft complete | Discovery standard + Jeremy prompt written. Reference implementation: [warrior-ai-web](https://github.com/Warrior-AI-Solutions/warrior-ai-web) |

---

## The Business Model

This system is designed to produce **six-figure project contracts**.

**The math:**
- A 2–4 hour discovery session produces a live stakeholder site
- That site demonstrates the depth and quality of our work before the contract is signed
- Skills 1+2 produce a scoped, priced, ROI-backed proposal
- Skill 3 makes it beautiful and real
- The client experiences the result of working with us before they've committed

**Price point target:** €50,000–€150,000+ per implementation engagement
**Monthly recurring:** Hosting, monitoring, updates, Warrior AI management fee

---

## How to Use This Repo

**For new client engagements:**
1. Run Skill 1 session → product brief
2. Run Skill 2 session → technical scope
3. Run Skill 3 session (or combined) → OMI transcript → Jeremy generates site
4. Launch site → send URL to all stakeholders
5. Close the deal

**For development of the skills:**
- Add session outputs to `skill-*/sessions/`
- Log sparring sessions in `sparring/`
- Open issues for gaps, contradictions, improvements
- PRs for refinements to any skill document

---

## Team

**Warrior AI Solutions**
- Steffen — Strategy, client relationships, product vision
- Weston — Design, Flutter implementation, technical execution
- Jeremy — AI infrastructure, site generation, skill execution

---

*Built on: 2026-02-25*
*Version: 0.1.0 — Foundation*
