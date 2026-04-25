# Axiom Intelligence Strategy Group — Content Creator Service Line

This directory contains the durable build-out of Axiom's productized service offering for content creators. It is designed so any future Claude session can read this folder and continue the work without re-explaining context.

## Read this first if you're a new session

1. Open `build/state.md` — it tells you what's done, what's in progress, what's next.
2. Open `build/checklist.md` — the master tracker.
3. Open `build/decision-log.md` — every meaningful decision, with reasoning, in date order.
4. Then proceed with whatever the current task is.

## What this service is

A productized retainer service that gives content creators a "studio in a box" — a team of eight specialized AI agents wired together with a creator's brand voice, asset library, CRM, and analytics. Axiom sells **integration, supervision, and the feedback loop** — not the underlying tools.

Three tiers: **Foundation**, **Studio**, **Empire**. See `service/offering.md`.

## Folder map

| Folder       | What lives here                                                              |
| ------------ | ---------------------------------------------------------------------------- |
| `service/`   | The offering itself — tiers, pricing, deliverables                           |
| `agents/`    | One file per agent role with mission, prompts, SOPs, KPIs, failure modes     |
| `sops/`      | Cross-agent operating procedures: onboarding, weekly cadence, quality bar    |
| `sales/`     | Discovery scripts, proposals, objection handling, case-study templates       |
| `build/`     | Roadmap, master checklist, current state, decision log                       |

## Operating principles (don't violate without writing it down)

1. **Recurring revenue, not project work.** Every tier is monthly retainer. Onboarding is a separate fixed-fee sprint.
2. **Pass-through tool costs, never bundled.** Client brings their own ElevenLabs, Runway, etc. Axiom margins die otherwise.
3. **Templated stack per tier.** New client = clone template, swap brand assets. No bespoke work after onboarding.
4. **Human-in-the-loop is the product.** Agents draft, humans approve. That's the brand-safety guarantee clients pay for.
5. **The Analyst → Strategist loop is the moat.** Most agencies don't close it. We do.
6. **Dogfood on Axiom's own channel** (and on the founder's 139K-follower IG) — that's the case-study reel.
