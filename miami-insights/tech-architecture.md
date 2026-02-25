# Warrior AI Solutions — Technical Architecture
## Miami Sessions: Synthesized Architecture Insights

> **Source:** 5 OMI conversation recordings from Miami (2026-02-22 / 2026-02-23)
> **Written:** 2026-02-25
> **Status:** Canonical reference — supersedes prior scattered notes

---

## 1. Source Conversations

| Conv ID | Title | Date |
|---------|-------|------|
| `fea47821-0c9a-4a0d-962c-493a382269e5` | Audit der Warrior AI / Omi Codebasis | 2026-02-23 |
| `b2d9c7d5-5975-401a-833b-54d974f51aeb` | Technische Architektur- und Integrationsentscheidungen für Warrior Skill | 2026-02-23 |
| `14ee65f2-2a31-41cd-afba-c6a4690b945f` | Team Klärt App-Architektur Und Datenlayer | 2026-02-22 |
| `50c0aed7-2ca0-4c4c-8a10-fd101d358986` | Datenlayer-Architektur für die neue Voryo-AI-App | 2026-02-22 |
| `7bc32de6-3488-4573-9808-c72d8aa50dbe` | Stripe–GoHighLevel Zahlungsintegration | 2026-02-23 |

---

## 2. Infrastructure Stack Decisions

### Cloud Provider
- **Warrior AI Solutions = Vultr** (NOT Hetzner)
- Hetzner is Steffen's private personal infrastructure only
- This was a canonical drift issue discovered during the codebase audit — all Hetzner references in Warrior AI repos must be replaced with Vultr

### Access & Networking
- **TwinGate VPN** for accessing Vultr-hosted Diffie instance
- Diffie accessible via custom alias URL (e.g. `vultr.diethe...`)

### Services Stack Summary
| Service | Role | Status |
|---------|------|--------|
| Flutter App | Thin client (UI + BLE only) | Active |
| Diffie CE | AI logic / coaching intelligence layer | Active on Vultr |
| Firebase Firestore | Primary data store | Active (us-central1) |
| Hono/Firebase Bridge | TypeScript security bridge, Port 4000 | Deployed |
| Qdrant | Vector DB for methodology rack | Deployed |
| Redis | Caching layer with domain-specific TTLs | Active |
| ElevenLabs | Voice API (160 voices, 24hr speech-to-text) | Integrated in Diffie |
| GoHighLevel | Reporting/KPI mirror only | Active (NOT payment processor) |
| Stripe | Primary payment processor | Active |

---

## 3. Data Architecture & Layer Separation

### Core Principle
**ALL coaching intelligence lives in Diffie — NOT in the Flutter app.**
The Flutter app is a thin client: UI rendering and BLE (Bluetooth Low Energy) connectivity only.

### Data Flow
```
Flutter App (thin client)
    ↕ BLE / REST
Hono/Firebase Bridge (TypeScript, Port 4000)
    — Zod schema validation on all writes —
    ↕
Firebase Firestore (primary data store, us-central1)
    ↕ read-only service account JSON
Diffie CE (AI logic layer)
    ↕
Qdrant (vector search — methodology rack)
Redis (caching layer)
```

### Direct LLM → Firebase Writes: FORBIDDEN
Security decision: LLMs (Diffie agents) are NOT permitted to write directly to Firebase. The Hono bridge is mandatory as a second security layer with Zod validation before any write reaches Firestore.

### Firebase Auth
- **Firebase Auth chosen over Clerk** (Decision C1)
- Reason: existing customers must not need new login credentials
- No migration burden on live user base

### Firebase Region
- **us-central1** (Decision C2)

### User Stack Vectorization Strategy
- ~1.8 million user stacks exist — NOT fully vectorized
- Strategy: **LLM summaries are vectorized**, not raw stacks
- Vector fields per entry: `date`, `domain/theme`, `who/what`, `brief situation`, `lesson learned`, `link to full stack`
- Full stacks only loaded from Firestore for the **top 5-10 semantic search results**
- Rationale: Firebase native vector store rejected — poor for time-based queries (e.g. "my stack from last week")

### Embedding Model
- **NOT YET DECIDED** (Decision C3 — open)
- Jeremy tasked with producing a decisive overview of options

### Offline Capability
- **v0: online-first** (Decision C4)
- **v1: offline-capable** (planned, not immediate)

### Redis Caching
- Domain-specific TTLs in use
- TTL duration questioned during sessions as potentially too short — needs review

---

## 4. Integration Patterns (Payments, CRM, Comms)

### Payment Architecture: Stripe + GoHighLevel

**Canonical Decision:** Stripe = primary payment processor. GoHighLevel = reporting/KPI mirror only.

#### Why NOT GoHighLevel for payments
- GoHighLevel subscriptions **cannot be created via API** (confirmed via research)
- Customer portal UX is 5–6 clicks deep — unacceptable UX
- Cannot handle the full subscription management lifecycle in-app

#### Why Stripe
- "Very, very good manageable through API, and agents can do all that"
- Full subscription lifecycle manageable programmatically
- Refunds handled directly via Stripe

#### Payment Flow
```
User (in-app) → Stripe direct → webhook → `record order payment` endpoint (GoHighLevel)
```

#### User Experience Principle
- **User NEVER leaves the app during payment** (Steffen's explicit requirement)
- Open trade-off: Stripe Checkout (redirects) vs in-app Stripe SDK (no redirect) — decision pending

#### GoHighLevel Role
- Accounting
- KPIs and controlling
- Customer support visibility
- Receives payment webhooks for reporting purposes only

---

## 5. AI Agent Technical Infrastructure

### The 7 Canonical Architecture Facts (from Audit session)

1. **Omi Flutter app** = base code, forked (not built from scratch). All 7 Omi platform systems inherited:
   - Plugin marketplace
   - Subscription engine
   - Door system
   - Plugin SDK
   - Core four pattern intelligence
   - Mission briefings
   - Live connection hub

2. **Diffie CE** = AI logic layer. ALL coaching intelligence lives in Diffie, NOT in the app.

3. **Firebase** = data layer. App writes via **Hono/Firebase Bridge, TypeScript, Port 4000** (already deployed).

4. **Flutter app** = thin client — UI and BLE only.

5. **AI agent teams write code**, not human engineers.

6. **Agent router** = only system still under evaluation.

7. **Qdrant** = vector DB for methodology rack (already deployed).

### Missing Agent Prompt Files
Two prompt files are blocked on Garrett's input before they can be created:
- **Canonical Drift Check Agent**
- **Canonical Breakthrough Agent**

Routing to coordinator only activates AFTER these prompt files exist.

### Agent Decision Process
- Decisions captured via "Human Decisions" ticket (WAR AI #42)
- Steffen / Weston answer via Omi transcription
- Jeremy converts answers to ADRs

### Data Permission Model (Planned)
Users will control granularly what data coaches can access:
- All data
- Submitted data only
- Specific stacks

### Proactive vs Reactive Design
- Current Omi: reactive and data-overloaded, no clear use case
- Planned pivot: **voice-first, proactive design**

### ElevenLabs Voice Integration
- Diffie has native ElevenLabs integration
- 160 voices available
- 24-hour speech-to-text capability

---

## 6. Security Architecture

### Credentials in Repo
- **Plaintext credentials in repository — intentional by design**
- Explicitly stated: "they will stay there because it is by design"
- This is a known, accepted architectural decision

### Bridge Security Layer
- Zod schema validation at the Hono bridge before any Firebase write
- Bridge acts as second security layer between LLM and database

### Firebase Service Account
- Read-only service account JSON for Diffie agents pulling user data from Firebase
- Write path always goes through bridge, never directly from LLM

---

## 7. Multi-Tenant / Client Scaling Considerations

### Current State
- ~1.8 million user stacks in the system
- Vectorization strategy designed to scale (summaries, not raw stacks)
- Redis caching with domain-specific TTLs for performance

### Planned
- Granular data permission model per user
- Voice-first proactive design to reduce noise / increase signal

---

## 8. Canonical Architecture (What's Proven & Deployed)

| Component | Status | Notes |
|-----------|--------|-------|
| Hono/Firebase Bridge (Port 4000) | ✅ Deployed | TypeScript, Zod validation |
| Firebase Firestore (us-central1) | ✅ Active | Primary data store |
| Firebase Auth | ✅ Active | Replaces Clerk |
| Qdrant | ✅ Deployed | Methodology rack vector search |
| Diffie CE on Vultr | ✅ Active | All AI logic lives here |
| Flutter app (forked Omi) | ✅ Active | Thin client |
| Redis caching | ✅ Active | Domain-specific TTLs |
| ElevenLabs in Diffie | ✅ Integrated | 160 voices |
| Stripe payments | ✅ Active | Primary processor |
| TwinGate VPN | ✅ Active | Vultr access |

---

## 9. Anti-Patterns (What Was Abandoned & Why)

| Abandoned | Replaced By | Reason |
|-----------|-------------|--------|
| React Native / Expo | Flutter | Complete pivot. Expo work archived as frontend reference only. |
| Weaviate | Qdrant | All Weaviate references must be stripped from codebase. |
| Cherry-picking Omi patterns | Full system inheritance | Pivoted during Miami weekend — all 7 Omi systems now inherited |
| Direct LLM → Firebase writes | Hono bridge (mandatory) | Security concern — LLMs must not write directly to DB |
| Firebase native vector store | Qdrant | Poor for time-based queries ("my stack from last week") |
| GoHighLevel as payment processor | Stripe | API cannot create subscriptions; customer UX is 5-6 clicks deep |
| Clerk auth | Firebase Auth | Existing customers would need new login credentials |
| Hetzner (for Warrior AI) | Vultr | Hetzner is Steffen's personal server only |

---

## 10. Deployment & Operations

### Audit P1 Fixes Required
Items identified during the codebase audit that must be remediated:

1. Replace all **React Native** references with Flutter
2. Replace all **Hetzner** references with Vultr (in Warrior AI repos)
3. Replace Firebase placeholder URLs with **Hono/Warrior Firebase Bridge** in all 5 ChatGPT call locations
4. Remove all **Weaviate** references
5. Add superseded banners to old research files
6. ADRs 15–19 marked as superseded/disabled
7. Fix **duplicate ADR numbers**
8. ADR W015 (provider decision) marked superseded in favor of Firebase
9. Cherry-pick pattern documentation rewritten to "full system inheritance"

### ADR Governance
- Architecture decisions captured as ADRs
- Human decisions (Steffen / Weston) collected via Omi transcription → Jeremy converts to ADRs
- Ticket: WAR AI #42

---

## 11. Cost Structure Signals

- Vultr: primary compute hosting (vs AWS/GCP which are not in stack)
- ElevenLabs: API usage-based (160 voices, 24hr STT)
- Stripe: transaction fees (standard processing)
- GoHighLevel: subscription cost maintained for reporting/KPI use case
- Qdrant: self-hosted on Vultr (no managed vector DB cost)
- Firebase: usage-based (Firestore reads/writes/storage)
- Redis: self-hosted on Vultr

**Cost optimization principle:** Self-host everything possible on Vultr to minimize per-unit cloud costs at scale.

---

## 12. Raw Quotes (Verbatim, with Conversation ID)

> "they will stay there because it is by design"
> — Credentials in repo decision | Conv: `fea47821-0c9a-4a0d-962c-493a382269e5`

> "ALL coaching intelligence lives in Diffie, NOT in the app"
> — Canonical architecture fact #2 | Conv: `fea47821-0c9a-4a0d-962c-493a382269e5`

> "AI agent teams write code, not human engineers"
> — Canonical architecture fact #5 | Conv: `fea47821-0c9a-4a0d-962c-493a382269e5`

> "very, very good manageable through API, and agents can do all that"
> — Re: Stripe as payment processor | Conv: `7bc32de6-3488-4573-9808-c72d8aa50dbe`

> "subscriptions cannot be created via API"
> — GoHighLevel limitation (confirmed via research) | Conv: `7bc32de6-3488-4573-9808-c72d8aa50dbe`

> "user never leaves the app"
> — Payment UX requirement | Conv: `7bc32de6-3488-4573-9808-c72d8aa50dbe`

> "existing customers shouldn't need new login credentials"
> — Reason for Firebase Auth over Clerk (Decision C1) | Conv: `b2d9c7d5-5975-401a-833b-54d974f51aeb`

> "my stack from last week"
> — Example query that Firebase native vector store cannot handle (time-based) | Conv: `50c0aed7-2ca0-4c4c-8a10-fd101d358986`

> "1.8 million user stacks"
> — Scale context for vectorization strategy | Conv: `50c0aed7-2ca0-4c4c-8a10-fd101d358986`

---

## 13. Key Technical Questions for Client OS

These items remain open or require decisions before building:

| # | Question | Status | Owner |
|---|----------|--------|-------|
| 1 | Embedding model selection for Qdrant | **OPEN** (Decision C3) | Jeremy (produce decisive overview) |
| 2 | In-app Stripe SDK vs Stripe Checkout (redirect) — which handles "user never leaves app"? | **OPEN** | Weston / Steffen |
| 3 | Redis TTL durations — are they too short? | **NEEDS REVIEW** | Jeremy |
| 4 | Canonical Drift Check Agent prompt file | **BLOCKED on Garrett** | Garrett |
| 5 | Canonical Breakthrough Agent prompt file | **BLOCKED on Garrett** | Garrett |
| 6 | Agent router selection (only system still under evaluation) | **IN EVALUATION** | Team |
| 7 | Granular data permission model implementation details | **PLANNED (v1)** | Jeremy |
| 8 | Offline capability implementation | **PLANNED (v1)** | Team |

---

*Generated from 5 OMI Miami conversations. All architecture decisions reflect state as of 2026-02-23.*
