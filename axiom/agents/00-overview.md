# The Agent Team — Overview

Eight roles. Each role is one agent (or a small chain of agents working as one). Each has a single mission and a clear handoff to the next role downstream.

## The org chart

```
                    ┌──────────────┐
                    │  STRATEGIST  │  ◄────── (Analyst feeds back here)
                    └──────┬───────┘
                           │
                ┌──────────┴──────────┐
                ▼                     ▼
        ┌──────────────┐      ┌──────────────┐
        │  RESEARCHER  │      │ SCRIPTWRITER │
        └──────┬───────┘      └──────┬───────┘
               │                     │
               └──────────┬──────────┘
                          ▼
                   ┌──────────────┐
                   │   PRODUCER   │  (assets: b-roll, VO, music)
                   └──────┬───────┘
                          ▼
                   ┌──────────────┐
                   │    EDITOR    │  (assembly, captions, thumbs)
                   └──────┬───────┘
                          ▼
                   ┌──────────────┐
                   │ DISTRIBUTOR  │  (format, schedule, post)
                   └──────┬───────┘
                          ▼
                   ┌──────────────┐
                   │  COMMUNITY   │  (DMs, comments, leads)
                   └──────┬───────┘
                          ▼
                   ┌──────────────┐
                   │   ANALYST    │  ───┐
                   └──────────────┘     │
                                        │
                          (loop back to Strategist)
```

## The eight roles at a glance

| # | Role         | Mission (one line)                                                  | Tier inclusion       |
| - | ------------ | ------------------------------------------------------------------- | -------------------- |
| 1 | Strategist   | Decide what content gets made and why, every week                   | Foundation+          |
| 2 | Researcher   | Make every piece factual, sourced, and credible                     | Foundation+          |
| 3 | Scriptwriter | Turn ideas into platform-tuned scripts in client voice              | Foundation+          |
| 4 | Producer     | Generate or source every non-script asset (b-roll, VO, music)       | Studio+              |
| 5 | Editor       | Assemble, caption, and thumbnail every piece to ship-ready          | Studio+              |
| 6 | Distributor  | Format per platform, schedule, post, run A/B tests                  | Studio+              |
| 7 | Community    | Triage DMs/comments, capture leads, protect the brand               | Empire only          |
| 8 | Analyst      | Tell us what worked, why, and what to make next                     | Empire only          |

## How they're built

Each agent is **not** a single LLM call. Each is a small system with:

- A **system prompt** (in its agent doc, copy-pastable)
- **Inputs** it expects (from previous agent or human)
- **Tools** it can call (MCP servers, APIs, internal databases)
- **Outputs** it produces (in a defined schema)
- **A human review gate** before output flows downstream
- **KPIs** that get logged for the Analyst to review

## The handoff schema

Every agent passes a structured object downstream:

```yaml
piece_id: <slug>
client_id: <client>
status: <draft|review|approved|published>
upstream_agent: <previous role>
downstream_agent: <next role>
artifacts:
  - type: <script|asset|cut|post>
    location: <path or URL>
    metadata: {...}
notes:
  - <free-form notes from this agent>
review_required: <true|false>
review_assigned_to: <human name>
created_at: <iso timestamp>
```

This is what makes the pipeline durable. Any human or future agent can read the object and know exactly what stage the piece is at.

## Where humans sit

- **Strategist agent** has a human strategist supervising once per week (calendar approval).
- **Editor agent** has a human editor-supervisor approving every cut before it ships.
- **Community agent** flags edge cases to a human community manager; routine messages auto-respond.
- **Analyst agent** runs unsupervised; report goes to client + internal team for next-week planning.

## What each agent doesn't do

This list is as important as what they do. See each individual agent doc for explicit non-responsibilities. The pattern: agents have one job each. Scope creep kills pipeline reliability.
