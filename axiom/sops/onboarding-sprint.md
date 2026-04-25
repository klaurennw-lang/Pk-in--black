# Onboarding Sprint SOP

The onboarding sprint is a fixed-fee, fixed-duration engagement that precedes every retainer. It is the most important deliverable Axiom produces — everything downstream depends on these artifacts being right.

**Duration:** 2 weeks (Foundation), 3 weeks (Studio), 4 weeks (Empire).
**Output:** A "client config kit" that runs the agent stack for that client.

---

## Day-by-day schedule (Studio tier — 3 weeks; adjust scope for Foundation/Empire)

### Week 1 — Discovery & voice capture

**Day 1 (Mon) — Kickoff call (90 min)**
- Confirm scope, tier, deliverables
- Walk through the deliverables contract line by line
- Get access requests in motion (analytics, posting, CRM, asset library)
- Schedule the voice-capture session

**Day 2 (Tue) — Access plumbing**
- Complete platform connections (IG, TikTok, YT, X, LinkedIn, etc.)
- Set up shared drives / Notion workspace
- Provision Axiom-side internal config (client_id, asset bucket, db rows)
- Connect analytics APIs

**Day 3 (Wed) — Audience + business intake**
- 60-min interview: who's the audience, what business is behind the channel, what are quarterly goals
- 30-min: walk-through of last 6 months of best/worst performers (client narrates)

**Day 4–5 (Thu–Fri) — Voice capture**
- Pull last 100 published pieces (transcripts + posts)
- Voice scorer training run (build per-client model)
- Compile signature phrases, banned phrases, vocabulary distribution
- Draft v1 of brand voice doc (use `brand-voice-template.md`)

### Week 2 — Asset library + agent config

**Day 6 (Mon) — Asset library audit**
- Inventory existing brand assets (logos, fonts, color palette, music library, b-roll archive)
- Tag and upload to Axiom's asset DB schema
- Identify gaps; queue Producer to generate baseline assets

**Day 7 (Tue) — Edit style capture**
- 60-min review of 5 favorite pieces with client (what they love, what they wish were different)
- Document: cut pacing, transition library, color grade preference, lower-third style
- Draft brand edit style guide

**Day 8 (Wed) — Strategy intake**
- Confirm Q-goals, top 5 competitors, content cadence target
- Build initial competitor scan
- Generate v1 of content calendar (next 14 days)

**Day 9 (Thu) — Agent configuration**
- Customize each agent's system prompt with client variables
- Configure handoff routing
- Set up review queues for human-in-the-loop checkpoints
- Build per-client dashboard skeleton (Empire only)

**Day 10 (Fri) — Dry run #1**
- Push one full piece through the pipeline end-to-end
- Identify breakages, bottlenecks, voice misfires
- Log in `decision-log.md`

### Week 3 — Polish + handoff

**Day 11 (Mon) — Fixes from dry run**
- Address every item from Friday's run
- Tighten prompts, swap templates as needed

**Day 12 (Tue) — Dry run #2**
- Push 3 pieces through (mix of long + short form)
- Validate platform-specific output is correct
- Test community auto-replies in sandbox (Empire only)

**Day 13 (Wed) — Client review**
- Present everything from sprint to client
- Walk through: what they get each week, what they need to do, how to request changes
- Confirm SLA + delivery contract

**Day 14 (Thu) — Soft launch**
- Schedule first week's content for next Monday
- Brief assigned strategist + editor-supervisor on this client
- Confirm all access is working

**Day 15 (Fri) — Sign-off**
- Final retro
- Confirm retainer start date
- Onboarding sprint complete

---

## Sprint deliverables checklist

A sprint is not done until **all** of these exist and are validated:

- [ ] **Brand voice doc** (filled-in template, signed off by client)
- [ ] **Voice scorer model** (trained, validated against held-out client samples)
- [ ] **Brand edit style guide** (cut pacing, transitions, color, lower-thirds)
- [ ] **Asset library** (existing assets ingested, tagged, baseline gaps filled)
- [ ] **Agent prompts** (each of the 8 agents configured for this client; lower tiers config only the active agents)
- [ ] **Handoff routing** (set in workflow orchestrator)
- [ ] **Dashboard** (Empire only — live, populated, accessible to client)
- [ ] **CRM integration** (Empire only — leads route correctly)
- [ ] **Initial 14-day calendar** (delivered + approved)
- [ ] **Initial hook bank** (25 hooks, scored)
- [ ] **Initial trend brief** (1 page)
- [ ] **First 3 scripts drafted** (validated in dry run)
- [ ] **Posting credentials** (verified working on every target platform)
- [ ] **Client kickoff doc** (single page summarizing what they receive, when, and how to give feedback)
- [ ] **Internal handoff doc** to retainer team (assigned strategist + editor-supervisor briefed)

---

## Pricing recap (from `service/pricing.md`)

| Tier        | Sprint price | Engineering hours allotted |
| ----------- | ------------ | -------------------------- |
| Foundation  | $4,500       | ~20 hrs                    |
| Studio      | $9,500       | ~40 hrs                    |
| Empire      | $15,000      | ~60 hrs                    |

If a sprint runs over allotted hours, that's a margin loss to Axiom — investigate root cause and template the missing piece for next time.

---

## Why the sprint matters more than any other deliverable

- The brand voice doc + voice scorer is what makes every script good. Skip it = generic content = client churn at month 3.
- The asset library schema is what makes Producer + Editor scale. Skip it = re-generation costs eat margin.
- The dry runs are what catch integration breakages before they show up in production. Skip them = first month is a fire drill, client loses confidence, churns.

**A sprint that's rushed produces a client that churns at month 4.** A sprint done right produces a client that stays for years and refers others.
