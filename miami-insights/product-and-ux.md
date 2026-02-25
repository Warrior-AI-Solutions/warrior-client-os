# Miami Insights: Product Strategy & UX

> Extracted from 5 OMI conversations, Miami, Feb 22–25 2026
> Focus: Client OS lens — product patterns, onboarding, personas, agent architecture

---

## Source Conversations

| Conv ID | Date | Title |
|---------|------|-------|
| fa652dd6 | 2026-02-25 | Onboarding-Konzept und Produktstrategie für Warrior App |
| 4a62c894 | 2026-02-24 | Team-Meeting zu Kundenkommunikation, Events und AI-App |
| 825af455 | 2026-02-23 | Produkt- und UX-Planung für Omi-App mit Agenten-Framework |
| ee80242d | 2026-02-24 | Garrett Plant Warrior AI Coaching Ökosystem |
| ad14f534 | 2026-02-25 | Team-Meeting zu AI, Klarheit und Vorbereitung auf Pivot-Event |

---

## Onboarding Patterns & Anti-Patterns

### ✅ What Works

**Three first-week activation mechanisms** (research-backed, from fa652dd6):
1. **Daily scheduled routine** — time-triggered reminders that create habitual touchpoints
2. **Emotional hook** — win/loss events that trigger app use at moments of high motivation
3. **Social connection** — apps hitting all 3 in Week 1 have very high retention

**Progressive disclosure** is non-negotiable:
- Day 1: Only identify which RAID domain needs the most work — nothing else
- Week 1: Just stacking and one action type
- Weeks 2–3: Introduce additional concepts step by step
- "We take our time to introduce them into new systems step by step by step" (fa652dd6)

**Onboarding agent** (from ee80242d):
- Walks new users through "The Door" and Core 4 concepts
- First 3 weeks: strict progressive disclosure
- Does NOT dump the entire system on day 1

**Emotional anchoring**:
- First quick wins are essential — must feel progress in first session
- Community connection in first week creates accountability/identity

### ❌ Anti-Patterns (What NOT to Repeat)

**The Hammer Problem** (fa652dd6):
- Data showed Fact Maps correlated with high retention
- Conclusion drawn: "everyone must have Fact Maps immediately"
- Result: overwhelming onboarding, terrible UX for new users
- Lesson: "When all you have is a hammer, every problem is a nail"
- Data-driven ≠ user-centered

**"Here's the system. Do it."** (ee80242d):
- Prior onboarding was overwhelming — assumed users could absorb everything at once
- Garrett has "unconscious competence" — doesn't remember what it's like to be new
- Core 4 basics need to be explicitly taught; Garrett no longer teaches them consciously

**Complexity at purchase** (fa652dd6):
- Selling full app ($197/month with everything) as entry product = too complex
- New model: **Power Pack** as entry (focused on stacking + RAID breakthroughs)
- Power Pack is smaller, faster, immediately valuable

**Bible Stacking as top-of-funnel** (fa652dd6):
- Bible Stacking entries convert poorly to paying Warrior customers
- Spiritual audience ≠ business performance audience
- Different channels, different messaging, different products

**The Lost Onboarding Doc Problem**:
- Prior onboarding documentation was destroyed/lost
- Team had to rebuild from scratch
- Lesson for Client OS: Document everything, version it, never let it be single-source

---

## Client Persona Map

### Tier 1: Council Members ($50k/year)
- Primary target for AI implementation
- Business owners with operational complexity
- Want AI that works inside their existing business systems
- High expectation for white-glove onboarding and support
- Personal support numbers given (Marcus model)

### Tier 2: Savage Members
- Performance-focused, action-oriented
- Respond to gamification (badges, rankings, visible status at live events)
- Wearables tier: **Silver** for Savage
- Want to measure progress publicly — "win board" matters

### Tier 3: Forge / General Members
- Mass market, lower touch
- Need pure self-serve + automated support
- Wearables tier: Plastic/standard
- Power Pack is the right entry product

### The "Kings" Persona (from ee80242d — strategic vision):
- Trusted entrepreneur clients who can "dock" their AI agents into the Warrior platform
- They bring their business systems; Warrior provides the AI infrastructure
- High trust required — Brotherhood ethos, not just customers
- Target for 6–7 figure implementation contracts

### Persona Anti-Patterns:
- **Bible Stackers** → different audience, different product, don't funnel into Warrior business programs
- **New users treated like advanced users** → progressive disclosure required, personas need different entry points

---

## Product Structure (Programs, Tiers, Features)

### Current Product Hierarchy

```
Warrior Platform
├── Power Pack (NEW entry product)
│   ├── Daily Stacking
│   └── RAID Breakthroughs
│       ├── Radical Responsibility
│       ├── Authentic Swing
│       ├── Impossible Game
│       └── Daily Attacks
├── Full App (Post-Power Pack)
│   ├── Fact Maps
│   ├── Mission Tracking
│   └── Impossible Games
├── Programs
│   ├── Forge (entry)
│   ├── Savage (~$10k/year)
│   ├── Council ($50k/year)
│   └── War Room (1:1 add-on/upsell)
└── Wearables
    ├── Gold (Council)
    ├── Silver (Savage)
    └── Plastic (general)
```

### Core 4 Framework (Garrett's methodology):
- **Body** — physical health/performance
- **Being** — identity/mindset
- **Balance** — relationships/family
- **Business** — professional performance

App teaches Core 4 explicitly — users must understand the framework before they can use it well.

### Measurement Levels (from ee80242d):
- **L1 — Quantity**: Did you do the work? (stack, track, map, attack)
- **L2 — Quality**: Did the work have gravitas/weight? (compared to top 20–30 power user reference stacks)
- **L3 — Outcome**: Did you actually win the quarter / Impossible Game?

### Gamification System:
- Badges earned for streaks — permanently part of "arsenal"
- Belt-ranking system visible at live events
- Win board shows completed actions publicly
- Community visibility drives accountability

---

## Agent Architecture Patterns

### Three Core AI Coaching Agent Roles (from ee80242d)

```
User Data Spine (all wearable + behavioral data)
         │
    ┌────┴────┐
    │         │
    ▼         ▼
Breakdown   Breakthrough
 Coach        Coach
    │         │
    └────┬────┘
         │
         ▼
   Mission / Success
     Evaluator
```

**Breakdown Coach**:
- Focuses on QUALITY of work
- Compares user stacks against top 20–30 power user reference stacks
- "Did this stack have gravitas? Did it have weight?"
- Identifies where the user's execution falls short

**Breakthrough Coach**:
- Focuses on QUANTITY / completion
- "Did you do the work at all? Did you stack, track, map, attack?"
- Tracks streaks, completion rates, action frequency
- Gamification trigger — awards badges

**Mission/Success Evaluator**:
- Quarterly-level assessment
- "Did you actually win the quarter? Did you complete the Impossible Game?"
- Connects daily actions to long-term outcomes

### Additional Specialist Agents Mentioned:
- **Power Stack Agent** — analyzes stack quality
- **Production Agent** — tracks business output
- **Fact Map Agent** — manages knowledge/belief mapping
- **Sales Authority Agent** — supports sales-related actions
- **Onboarding Agent** — progressive first-3-weeks experience
- **Coordinating Agent** — watches all wearable feeds, triggers specialist agents

### Bot Architecture Decision Point (fa652dd6):
**Open question being debated**: 7 separate specialized bots vs. one bot with variable workflows
- Expert recommendation: **Separate bots** for different onboarding flows
- Reason: Clarity — each bot knows its scope, no context confusion
- Risk of single-bot approach: Prompt complexity grows unbounded, hallucination risk increases

### The Omi Problem → AI Framework Solution (825af455):
- **Omi without framework** = reactive data collection tool, "nothing useful"
- **Omi WITH coaching framework** (Jeremy/Diffie) = genuinely valuable
- Key insight: "It's not the AI itself in and of itself. It's not the value. The value is AI embedded in the coaching framework"
- This is the Client OS thesis: AI + methodology = the product. AI alone = commodity.

---

## Communication & Support Design

### Current State: Chaos (4a62c894)
- 5–6 different numbers/people contacting same client
- Personal phones given to Council/Savage as workaround
- Clients don't know "who to contact regarding what theme"
- No unified communication channel
- HelpScout for email, GoHighLevel for SMS — disconnected

### Desired Future State:
- Single unified channel for all client communication
- Intelligent routing to right person/system
- Zendesk-like ticket system
- BI dashboard for support reporting

### Marcus Ownership Model (interim solution):
- All active clients switched to Marcus in GoHighLevel (single ownership)
- Tags in GHL control handoff from Sales → Marcus (Support)
- Separates closer role (revenue-generating) from support role (relationship-maintaining)
- Pattern: **Closers close, Support supports** — never mix roles

### Tier-Differentiated Support:
- Savage/Council: elevated response, personal touch, direct access
- Forge/General: automated, self-serve first
- Pattern: support tier should match investment level

### The Role Confusion Problem (05296712, 2b7e7b0b):
- When salespeople (Marcus, Steven) do support work → their sales authority is undermined
- Students associate outreach with money demands → trust erodes
- Clear handoff = cleaner sales process AND better support experience

---

## Feedback & Measurement Systems

### 15–20% AI Coaching Engagement (from ee80242d):
- 200 conversations in January → 15–20% respond to AI coaching prompts
- This is the baseline — target is to increase it
- Triggers: emotional state shifts, drift detection, milestone completions

### Drift Detection System (825af455):
- App detects when user enters "drift" (behavioral/emotional pattern)
- With permission: notifies coach/trainer
- Creates proactive intervention instead of reactive support

### Permission/Data Sharing Model (825af455):
- **Full share**: everything goes to coach
- **Submitted content only**: only explicit submissions shared
- **Stacks only**: just the daily stack content
- User controls the data flow — builds trust

### Current Support Tracking (ad14f534):
- Marcus doing temporary Excel tracking (client, date, problem, solution)
- Future: BI dashboard in app (HelpScout + Metabase or similar)
- Long-term: all support in Warrior App itself

---

## Content & Community Strategy

### Video Production Pattern (4a62c894):
- B-roll + 30-second quarterly goal statements captured at every Quarterly event
- "Year in Review" film compiled at year-end for each warrior
- Creates strong community narrative, emotional retention
- Also works as marketing asset (with permission)

### Community Content Strategy:
- Win board = public visibility of completed actions
- Belt rankings visible at live events = social proof + accountability
- Brotherhood content is pull (warrior wants to share) not push (marketing demands it)

### AI Echo Chamber Warning (ad14f534):
- Poorly worded prompt → AI told men their quarterly pivots instead of guiding the discovery
- All men accepted AI output without critical evaluation
- Risk: "prompt your way into an echo chamber"
- Mitigation: human-led framework + AI as assistant, not driver
- Check-in frequency increasing (3x/day not weekly) because AI moves fast enough that 1-degree drift = massive divergence

---

## Failure Modes (What NOT to Repeat)

| Failure | What Happened | Lesson for Client OS |
|---------|--------------|---------------------|
| Hammer Problem | Fact Map data → forced on everyone | Don't optimize features, optimize user journey |
| Lost Documentation | Onboarding docs destroyed | Every doc versioned, backed up, never single-source |
| Unconscious Competence | Garrett can't see what's hard for new users | Personas must include "new user" lens always |
| Misaligned AI Prompts | "Find your pivot" → AI assigned pivots | Prompts must guide, not prescribe |
| Bible Stacking Funnel | Different audience, wrong product | Know your ICA, don't assume all spirituality = business performance |
| Communication Chaos | 5-6 contact points for same client | Unified channel from day 1 |
| Role Confusion | Closers doing support = authority erosion | Hard separation of sales and support roles |
| Old Product Complexity | Full app as entry product = overwhelming | Lead with simplest valuable version |
| Data-Driven Onboarding | Retention metric drove feature decisions | UX must be user-centered, not metric-centered |

---

## Raw Quotes (Verbatim, with Conversation ID)

**On Power Pack focus** (fa652dd6):
> "It is the power pack, which just focuses on your stacking and using your RAID to have breakthroughs."

**On three activation mechanisms** (fa652dd6):
> Research finding: Apps hitting all 3 of (daily routine, emotional hook, social connection) in Week 1 have very high retention. "We take our time to introduce them into new systems step by step by step."

**On the Hammer Problem** (fa652dd6):
> "When all you have is a hammer, every problem is a nail." — Applied to over-indexing on Fact Maps because data showed correlation with retention.

**On Omi without framework** (825af455):
> "I wouldn't have it without Jeremy." [on Omi without the AI coaching framework being worthless]

**On where the real value is** (825af455):
> "It's not the AI itself in and of itself. It's not the value." — The value is the AI embedded inside the methodology framework.

**On action pivot** (ee80242d):
> "We've pivoted it all to action action action action action." — Garrett's description of the shift from data collection to action measurement.

**On AI echo chambers** (ad14f534):
> Poorly worded prompt example: "find my quarterly pivot" → AI told the men what their pivots were instead of guiding them to discover it themselves. All accepted without pushback.

**On speed and alignment** (ad14f534):
> "You need to stay vibrationally above your AIs." — Human clarity must lead AI direction. Agents move so fast that 1-degree misalignment = massive drift over hours.

**On the Acceleration Age** (ee80242d):
> In 5 days the team achieved results planned for 3–4 weeks. AI acceleration means daily stacking and check-ins are more important than ever.

**On communication chaos** (4a62c894):
> "There is no unified communication channel" — clients getting messages from 5-6 different numbers, don't know who to contact for what.

---

## Key Questions This Raises for Client OS

1. **Onboarding design**: How do we apply the three-activation-mechanism framework to the Client OS delivery? What's the client equivalent of "first week"?

2. **Progressive disclosure for businesses**: The Power Pack model (smallest valuable unit first) should map to the Client OS delivery. What's Phase 1 that delivers immediate value before full implementation?

3. **Separate bots for separate workflows**: Should Client OS deliver separate AI agents per business function (sales, support, ops) rather than one general-purpose agent?

4. **The Omi Lesson for Client OS**: Every client will have existing tools (CRM, comms, support). The AI framework embedded IN their existing workflow = value. AI bolted on top = commodity.

5. **Documentation persistence**: The "lost onboarding docs" failure should drive us to build documentation-first into every engagement. Client OS deliverable = living docs, not one-time setup.

6. **Role separation at scale**: As we take on clients, who is the "closer" and who is the "Marcus"? Steffen closes, Jeremy operates? Define the handoff protocol.

7. **Measurement from day 1**: L1/L2/L3 measurement framework (quantity → quality → outcome) should be designed into every Client OS engagement upfront. Don't wait to measure.

8. **AI echo chamber prevention**: How do we ensure client businesses don't build AI systems that just confirm what leaders want to hear? This is a real product risk.

9. **Unified communication layer**: Every enterprise client we implement for will have communication chaos (like Warrior). The Client OS should include a Chatwoot/unified channel component by default.

10. **Content and proof building**: Warrior's video testimonial / Year in Review pattern is highly replicable. Client OS should include systematic case study capture from day 1 of every engagement.
