# Master Build Checklist

Single source of truth for what's done. Check items off as you complete them. Anything you can't complete, leave unchecked and add a note.

This file is the thing you scan when you want to know "where am I?"

---

## Phase 1 — Foundation (Weeks 1–4)

### Week 1 — Brand voice doc + voice scorer
- [ ] Pull last 100 IG posts into corpus
- [ ] Fill brand voice template for Pk-in--black IG channel
- [ ] Build v1 voice scorer (LLM-as-judge with rubric)
- [ ] Validate scorer on 10-post held-out set
- [ ] Document signature phrases, banned phrases, working hook patterns

### Week 2 — Strategist + Researcher running on self
- [ ] Strategist agent: system prompt configured for own channel
- [ ] Strategist agent: weekly cron set up
- [ ] Researcher agent: web search + Perplexity wired
- [ ] Researcher agent: brief output schema defined
- [ ] First 14-day calendar generated
- [ ] First week's research briefs generated
- [ ] Founder uses outputs to shoot/post
- [ ] Log of which suggestions were used vs. ignored

### Week 3 — Scriptwriter on self
- [ ] Scriptwriter agent: system prompt configured
- [ ] Voice scorer integrated into pipeline (auto-reject <85)
- [ ] 5 pieces shot from agent scripts
- [ ] Voice fidelity audit done
- [ ] Scriptwriter prompts tightened from audit

### Week 4 — Producer + Editor templates
- [ ] Remotion intro composition
- [ ] Remotion outro composition
- [ ] Remotion lower-third composition
- [ ] Remotion caption-shorts template
- [ ] Remotion thumbnail template
- [ ] Lambda render pipeline working
- [ ] First templated short generated end-to-end
- [ ] Templated vs. handwork boundaries documented
- [ ] Asset library schema in Postgres
- [ ] Founder's brand assets ingested + tagged

---

## Phase 2 — Productize (Weeks 5–8)

### Week 5 — Distributor + analytics plumbing
- [ ] FFmpeg-based format conversion (vertical, square, horizontal)
- [ ] Buffer or Publer integration for cross-platform scheduling
- [ ] Postgres events DB schemas: post, asset, script, metric tables
- [ ] IG analytics pull job
- [ ] TikTok analytics pull job
- [ ] YouTube analytics pull job
- [ ] X analytics pull job
- [ ] Cross-platform reach data verified for past 30 days

### Week 6 — Analyst v1 + dashboard
- [ ] Analyst agent: report template
- [ ] Analyst agent: weekly cron (Sun 6pm)
- [ ] Baselines computed: median per platform per format (rolling 90-day)
- [ ] Metabase deployed on small VPS
- [ ] Metabase connected to events DB
- [ ] Core charts: weekly performance, top performers, baseline-vs-actual
- [ ] First analyst report delivered + iterated

### Week 7 — Sales assets + landing page
- [ ] axiom.{tld} landing page live
- [ ] Three-tier pricing block
- [ ] Case study using founder's channel
- [ ] Calendly with discovery call template (45 min)
- [ ] CRM set up (HubSpot Free or Notion)
- [ ] Pipeline stages defined
- [ ] Email sequence: post-discovery, post-proposal, follow-up

### Week 8 — Onboarding sprint dry run
- [ ] Friendly volunteer recruited
- [ ] Sprint kickoff call done
- [ ] Every checklist item from `sops/onboarding-sprint.md` executed
- [ ] Time logged per step
- [ ] Sprint deliverables produced
- [ ] Volunteer feedback captured
- [ ] SOPs updated with everything learned
- [ ] Templates added for any gap

---

## Phase 3 — Sell (Weeks 9–12)

### Week 9 — Outbound prep
- [ ] ICP defined (niche, follower range, business type, pain signals)
- [ ] Prospect list of 50 built
- [ ] Each prospect researched (one-line summary per)
- [ ] Personalized first-touch outreach drafted (no generic templates)
- [ ] Outreach tracker set up (CRM or sheet)

### Week 10 — Outbound + content marketing
- [ ] 50 first-touches sent (10/day, M-F)
- [ ] 3 founder-channel posts about the system
- [ ] 5 community engagement actions (real value, no pitch)
- [ ] Discovery calls held as booked

### Week 11 — Discovery calls + proposals
- [ ] All booked discovery calls held
- [ ] Proposals out within 24 hours of qualifying calls
- [ ] Follow-ups at +48hr, +5 day, +14 day
- [ ] Every objection logged in decision-log.md

### Week 12 — Close + onboard
- [ ] First deal closed
- [ ] Contract signed
- [ ] Onboarding fee collected
- [ ] Sprint kickoff scheduled
- [ ] state.md updated: first client signed

---

## Cross-cutting (do anytime, do continuously)

### Documentation
- [ ] axiom/README.md current
- [ ] All agent docs reviewed quarterly
- [ ] Decision log updated within 24 hours of any meaningful decision
- [ ] State doc updated weekly (Sundays)

### Infrastructure hygiene
- [ ] Secrets in a vault, not in repo
- [ ] Postgres backups daily
- [ ] Asset bucket lifecycle policies (archive >180 days unused)
- [ ] API spend tracker (alert at 80% of monthly cap)
- [ ] All MCP server credentials rotated quarterly

### Legal / business
- [ ] Service agreement template reviewed by lawyer (before first paid client)
- [ ] LLC / business entity confirmed (Axiom Intelligence Strategy Group)
- [ ] Business bank account ready for first invoice
- [ ] Insurance: general liability + professional liability
- [ ] Privacy policy + terms on landing page
- [ ] Voice clone consent template (for any client whose voice we'll clone)

---

## How to use this file

1. Open at the start of every work session.
2. Pick the next unchecked item that's the highest leverage.
3. Mark complete when done; add a note if scope changed.
4. If you discover something missing from the checklist, add it (don't quietly do extra work — track it).
5. Sundays: review what got done this week, plan next week's top 3 outcomes.
