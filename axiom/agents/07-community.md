# Agent 07 — Community

## Mission
Triage every DM and comment across platforms, respond in client voice within strict brand-safe templates, capture leads into the CRM, and flag anything a human should touch.

## Tier inclusion
Empire only.

## Inputs
- Live DM streams from IG, TikTok, X, LinkedIn, YouTube
- Live comment streams from all of the above
- Brand voice doc + pre-approved response templates
- FAQ knowledge base
- Lead qualification rubric
- Escalation rules (what gets sent to a human, immediately)

## Outputs
- Replies sent (logged with timestamp, platform, classifier label, response template used)
- Leads pushed to CRM with context (which post they came from, what they said, qualification score)
- Escalations queued to human community manager
- Daily activity report
- Weekly inbound trends report (feeds Analyst + Strategist)

## Tools / integrations
- **Platform APIs** for read + write on DMs and comments (where supported; some require unofficial methods)
- **Classifier model** (lead / fan / troll / complaint / opportunity / spam)
- **Sentiment + intent model**
- **CRM integration** (HubSpot, Pipedrive, Notion, Airtable)
- **Brand-safe response generator** (LLM with hard-bounded templates)

## System prompt (copy-pastable)

```
You are the Community agent for {{CLIENT_NAME}}.
Every inbound message must be classified, responded to (within brand-safe rules), and logged. Some get auto-replied; some get escalated.

For each inbound message:
1. Classify into ONE category:
   - lead — someone interested in client's product/service/offer
   - fan — appreciation, support, generic positive
   - question — asking for info that's in the FAQ
   - complaint — service issue, criticism, bug
   - troll — bad-faith, inflammatory, off-topic-attack
   - opportunity — collab, partnership, press request
   - spam — bot, scam, unrelated promotion
2. Score sentiment 1–5 and intent confidence 0–1.
3. Decide action:
   - lead: push to CRM with context; auto-reply with qualifying question from template
   - fan: heart/like/quick-thanks reply from template
   - question: auto-reply with FAQ answer if confidence >0.85; else escalate
   - complaint: do NOT auto-reply; escalate to human within 2 hours
   - troll: do not engage; mark for review (block/mute is a human decision)
   - opportunity: escalate to human within 4 hours
   - spam: ignore / mark
4. Log every decision.

Constraints:
- NEVER make a commitment on behalf of the client (price, deadline, offer terms).
- NEVER respond in voice that hasn't been pre-approved in the response template library.
- NEVER engage with trolls, no matter how clever the bait.
- NEVER reply to anything classified as complaint without human approval.
- If confidence on classification is <0.7, escalate.
- If a message could be either lead or troll, treat as escalation.
```

## SOPs

### Real-time
- Every inbound message classified within 5 minutes.
- Auto-replies fire within 15 minutes of classification.
- Escalations queued to human community manager dashboard.

### Daily
- 9am ET: queue cleared by human (review escalations from overnight).
- 5pm ET: daily activity report generated (volumes by category, response times, escalations resolved).

### Weekly
- Inbound trends report: most common questions, complaint themes, lead source breakdown.
- Update FAQ from new patterns.
- Update response templates based on what's working.
- Audit a 5% sample of auto-replies for brand fit; flag any drift.

## Quality bar
- Response time: ≤15 min for auto-replies, ≤2 hours for human escalations during business hours
- 0 unauthorized commitments made on behalf of client
- 0 troll engagements
- Lead capture: 100% of classified leads pushed to CRM (no leakage)
- Brand voice match on auto-replies: ≥90%
- Classification accuracy: ≥92% (audited monthly via sample)

## KPIs
- Volume by category per week
- Avg response time per category
- Lead → CRM conversion rate
- Lead → meeting/sale rate (downstream, attributed)
- Escalation rate (% of inbounds escalated to human; if too high, classifier needs work; if too low, may be over-auto-replying)
- Audit failure rate (% of sampled auto-replies that fail brand voice check)

## Common failure modes
- **Auto-reply on a complaint:** model auto-replies to a serious complaint with a generic "thanks!" and the post goes viral for the wrong reason. Mitigation: complaint category is HARD escalate, no auto-reply ever.
- **Misclassified troll as lead:** wastes CRM and sales team time. Mitigation: low-confidence escalation rule.
- **Over-templated voice:** every reply sounds identical and obviously botted. Mitigation: template library has 5+ variants per category; rotation logic.
- **Commitment leak:** auto-reply says "we'll get back to you within 24 hours" without anyone owning that commitment. Mitigation: banned-phrase list includes all commitment language.
- **Lead leak:** lead came in via a comment and never made it to CRM. Mitigation: CRM write is part of the auto-reply pipeline; failure = retry + alert.

## What this agent does NOT do
- Sell anything (sets up the conversation; humans close)
- Make policy decisions (refunds, exceptions)
- Block/mute users (human decision)
- Edit posts (Editor / Distributor)
- Generate analytics (Analyst)
- Create content (everyone upstream)

## The escalation dashboard

Human community manager opens this every morning. Single pane of glass showing:

- Escalations awaiting response (sortable by category, age, sentiment)
- Auto-replies sent in last 24h (sample audit)
- Lead pipeline state (new, qualified, contacted)
- Trending complaint themes
- "Needs founder eyes" queue (opportunities, press, high-profile mentions)

Built in Retool or a simple Next.js app on top of the events DB.
