# Skill 2 — Technical Scoping

> **"How do we build it?"**
> Turn a product brief into a precise technical blueprint with credible estimates and a clear price.

---

## Status: 🟡 Spec In Progress

The vision is defined. The full session structure needs to be built out.
See `CLIENT-OS.md` for the complete vision. This README tracks Skill 2 specifically.

---

## Purpose

Skill 1 tells us *what* to build. Skill 2 tells us *how* — at the level of detail needed to price it confidently and deliver on promise.

Without Skill 2, we are guessing on price and scope. With it, we can stand behind every number we put on the `/offer` page.

By the end of a Skill 2 session, we have:
- A named architecture (every layer defined)
- A sprint/milestone breakdown (named, described, estimated)
- A technology stack (specific choices with rationale)
- A data flow (how information moves through the system)
- An effort estimate (total days, by track, with confidence range)
- A risk register (what could go wrong, what we do about it)
- A pricing model (upfront + monthly)

---

## Outputs

| Artifact | Description |
|----------|-------------|
| `architecture.md` | Layer-by-layer system design |
| `sprint-breakdown.md` | Named milestones with estimates |
| `stack-decisions.md` | Technology choices with rationale |
| `risk-register.md` | Risks + mitigations |
| `pricing-model.md` | Upfront + monthly cost calculation |

---

## Session Design

*Full session agenda: TBD*

**Planned sections:**
1. Architecture Overview — what are the layers, what connects to what
2. Frontend — what does the user touch, on what devices
3. Backend — where does the data live, what processes it
4. AI/ML Layer — is there AI, what model, what data does it need
5. Infrastructure — hosting, scaling, DevOps, monitoring
6. Integrations — every external system involved
7. Security — auth, data sensitivity, compliance requirements
8. Sprint Breakdown — natural phases, what each delivers
9. Effort Estimation — days per track, total
10. Risk Assessment — what could blow the estimate, what are the mitigations

---

## The Estimation Framework

Estimates are given in **tracks** (parallel work streams) and **phases** (sequential milestones):

```
Phase 1: Foundation
  ├── Track A: Backend/Infra    [X days]
  └── Track B: Frontend         [Y days]

Phase 2: Core Features
  ├── Track A: Backend          [X days]
  └── Track B: Frontend         [Y days]

Phase 3: Integration & Polish
  ├── Track A: Backend          [X days]
  ├── Track B: Frontend         [Y days]
  └── Track C: Security/QA      [Z days]
```

**Total elapsed time ≠ total days worked.** Parallel tracks compress calendar time.

---

## Sessions Log

| Date | Client | Output | Notes |
|------|--------|--------|-------|
| — | — | — | No sessions run yet |

---

## Open Questions

- How do we handle uncertainty in estimates? (Best case / worst case range?)
- At what level of detail should the sprint breakdown go into the site vs. staying internal?
- How do we scope AI components where the exact model/approach isn't decided yet?
- Should Skill 2 include a competitor analysis of the technical approach?

---

*Add session outputs to `sessions/` after each engagement.*
