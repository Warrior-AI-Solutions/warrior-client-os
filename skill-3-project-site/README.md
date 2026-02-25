# Skill 3 — Project Site

> **"Show it. Sell it. Ship it."**
> One OMI transcript → one live stakeholder site, deployed the same day.

---

## Status: 🟢 v1.0 Draft Complete

The discovery standard is written. The Jeremy prompt is written. The reference implementation is live.

**Reference implementation:** [warrior-ai-web](https://github.com/Warrior-AI-Solutions/warrior-ai-web)
*(Warrior Flutter App — the first project to go through this system)*

---

## Files In This Directory

| File | Description |
|------|-------------|
| `DISCOVERY-STANDARD-v1.0.md` | Complete session agenda with 8 sections, questions, verbal anchors |
| `JEREMY-PROMPT.md` | The full AI prompt: paste this + transcript → get site files |
| `site-template/` | VitePress starter template (coming — will be the blank starting point) |

---

## The Pipeline

```
Discovery Session (2–4h, OMI recording)
    → OMI transcript
        → Paste into Jeremy with JEREMY-PROMPT.md
            → VitePress files generated
                → New GitHub repo created
                    → Connected to Cloudflare Pages
                        → Site live
                            → URL sent to stakeholders
```

**Target time from session end to site live: under 2 hours.**

---

## Site Pages

| Page | URL | What It Shows |
|------|-----|---------------|
| Home | `/` | Hero, problem statement, team, status strip |
| Progress | `/progress` | Sprints/milestones, status badges, V0 gate |
| Architecture | `/architecture` | Technical layers, data flow, hosting |
| Security | `/security` | Security posture, compliance, auth model |
| QA / Success | `/qa` | Success criteria, metrics, sign-off conditions |
| Jira Tickets | `/jira` | Full ticket reference with board links |
| **Offer** | `/offer` | Investment, timeline, monthly cost, ROI, CTA *(coming)* |

---

## Design System

All project sites use the Warrior AI design system:

- **Background:** `#0A1628` (deep navy)
- **Accent:** `#C8A84E` (warrior gold)
- **Mode:** Dark only
- **Fonts:** Inter · JetBrains Mono · Playfair Display
- **Status colors:** Green `#059669` done · Gold `#C8A84E` active · Blue `#3B82F6` next · Gray `#6B7280` backlog

---

## Next Improvements

- [ ] Build the `/offer` page component (pricing, ROI, CTA)
- [ ] Create `site-template/` as a blank VitePress starter
- [ ] Test the pipeline end-to-end on a second client project
- [ ] Add image/screenshot support to the discovery standard
- [ ] Build a `warrior-client-os-template` repo for one-command project site setup

---

*v1.0 produced from the Warrior Flutter App engagement, 2026-02-25.*
