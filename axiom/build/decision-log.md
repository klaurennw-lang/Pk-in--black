# Decision Log

Every meaningful decision, in date order, with reasoning. This is how future sessions (Claude or human) know why things are the way they are.

Format: append new entries at the top. Each entry has date, title, decision, reasoning, alternatives considered, who decided.

---

## 2026-04-25 — Initial scaffold of /axiom service line

**Decision:** Build out a comprehensive `/axiom/` directory in the existing `Pk-in--black` repo (rather than creating a new repo) to house the productized service offering for Axiom Intelligence Strategy Group.

**Reasoning:**
- Founder's 139K-follower IG channel will be used as the dogfood / case study, so colocating the personal content HQ (existing `/ideas`, `/drafts`, etc.) with the service playbook keeps everything in one place during the build phase.
- A separate repo can be split out later if needed, but the friction now (single source of truth, single PR, single backup) outweighs the future organizational tidiness.

**Alternatives considered:**
- Separate `axiom-playbook` repo: rejected for now to avoid context-switching during build.
- Notion / Google Drive: rejected because version control, diff history, and AI agent compatibility are all stronger in git.

**Decided by:** Founder + Claude (initial build session)

---

## 2026-04-25 — Three-tier service structure (Foundation / Studio / Empire)

**Decision:** Productize the offering as exactly three tiers: Foundation ($1,800/mo), Studio ($6,500/mo), Empire ($18,000/mo). No à la carte. No additional tiers.

**Reasoning:**
- Three is the canonical SaaS-style packaging — entry, flagship, premium.
- À la carte kills margin and fragments delivery operations.
- Foundation is impulse-purchase territory for established creators; Studio is the flagship most clients will land in; Empire is the high-touch growth ladder priced like a fractional CMO.
- Pricing anchored above "freelancer" but below "agency."

**Alternatives considered:**
- 5 tiers: rejected — too many decisions for prospects, too much delivery variance.
- 1 tier: rejected — locks out smaller creators and ceiling-caps revenue.
- Custom-priced engagements: rejected — sales cycle too long, margins inconsistent.

**Decided by:** Founder + Claude

---

## 2026-04-25 — Pass-through tool costs, never bundle

**Decision:** All third-party tool costs (ElevenLabs, Runway, Submagic, Buffer, etc.) are pass-through — client provides their own API keys and gets their own bill. Axiom never marks up or absorbs.

**Reasoning:**
- Tool prices change too often to bundle reliably.
- Markup creates legal complexity (resale terms in some vendor TOSs).
- Pass-through preserves Axiom's gross margin (40–50%); bundling erodes it.
- Clients keep ownership of their accounts if they leave Axiom.

**Alternatives considered:**
- Bundle with 15% markup: viable, but not on first deals — adds it as an option for clients who request a single invoice.

**Decided by:** Founder + Claude

---

## 2026-04-25 — Eight-agent team architecture (not fewer, not more)

**Decision:** The agent team has exactly 8 roles: Strategist, Researcher, Scriptwriter, Producer, Editor, Distributor, Community, Analyst. Each has one job. Each handoff is structured.

**Reasoning:**
- Single-responsibility per agent keeps prompts focused and outputs reliable.
- 8 maps cleanly to the natural content lifecycle (idea → research → script → assets → cut → publish → engage → measure).
- Fewer agents = each does too much, prompts become unwieldy, failures harder to attribute.
- More agents = redundant handoffs, slower cycle time, more breakage.

**Alternatives considered:**
- One mega-agent: rejected — opaque, unpredictable, can't tier-gate features.
- 12+ agents: rejected — over-engineering for current scale.

**Decided by:** Founder + Claude

---

## 2026-04-25 — Onboarding as separate paid sprint, mandatory

**Decision:** Every client engagement begins with a paid 2–4 week onboarding sprint (priced separately from the retainer). No exceptions. Sprint produces the brand voice doc, voice scorer, asset library, agent prompts, dashboard.

**Reasoning:**
- The brand voice doc + voice scorer is what makes the rest of the system not generic.
- Skipping it = generic content = client churn at month 3.
- Separating it as a paid sprint lets us properly resource it without margin compression on month 1.
- High margin (~70%) on sprint, which improves over time as templates mature.

**Alternatives considered:**
- "Free trial" onboarding: rejected — undervalues the most important deliverable.
- Bundle into first month of retainer: rejected — month 1 becomes a fire drill, gross margin negative.

**Decided by:** Founder + Claude

---

## 2026-04-25 — Dogfood on founder's own 139K IG before selling

**Decision:** Phase 1 (Weeks 1–4) is dedicated to running the agent stack on the founder's existing IG channel as case study #1. No outbound sales until Week 9.

**Reasoning:**
- Prospects ask "have you done this for yourself?" — a real case study trumps any pitch deck.
- Building on a known channel surfaces breakages safely.
- Founder's voice doc is the easiest to validate (founder knows their own voice).
- Free training data and free proof of concept simultaneously.

**Alternatives considered:**
- Start outbound while building: rejected — selling something half-built risks reputation damage and burns hot leads on a non-deliverable.
- Skip dogfood, build for hypothetical client: rejected — no calibration target, no case study.

**Decided by:** Founder + Claude

---

## How to add a new entry

When you make any decision that future you (or future Claude) might second-guess, add an entry. Format:

```
## YYYY-MM-DD — Short title

**Decision:** [What you decided]

**Reasoning:** [Why]

**Alternatives considered:** [What you rejected, briefly why]

**Decided by:** [Who]
```

Append at the top. Don't edit old entries (decisions are immutable; if a decision changes, write a new entry that supersedes the old, and note which entry it supersedes).
