# Pricing & Margin Math

All numbers are USD, monthly recurring unless noted. Tool/API costs are pass-through to client (they bring their own keys); Axiom never marks them up or absorbs them.

---

## Tier pricing

| Tier         | Price (mo) | Onboarding sprint (one-time) | Min commitment |
| ------------ | ---------- | ----------------------------- | --------------- |
| Foundation   | $1,800     | $4,500                        | 3 months        |
| Studio       | $6,500     | $9,500                        | 3 months        |
| Empire       | $18,000    | $15,000                       | 6 months        |

**Why these prices:**
- Anchored above "just hire a freelancer" but below "hire a small agency"
- Foundation is impulse-purchase territory for any creator >50K followers monetizing
- Studio is the price point where serious creators stop comparing and start evaluating ROI
- Empire is priced as infrastructure, not service — the comparable is a fractional CMO ($15-25K/mo)

**Annual discount:** Pay 12 upfront, get 2 months free (16.6% off). Locks in revenue, kills churn.

---

## Margin math (per client, per month)

### Foundation — $1,800/mo

| Cost line                             | $/mo   |
| ------------------------------------- | ------ |
| Strategist (human, ~3 hrs/wk @ $75/hr)| $900   |
| Agent infrastructure (LLM, scrapers)  | $80    |
| Tooling (Notion, scheduling, etc.)    | $40    |
| **Total cost**                        | **$1,020** |
| **Gross margin**                      | **$780 (43%)** |

### Studio — $6,500/mo

| Cost line                                    | $/mo   |
| -------------------------------------------- | ------ |
| Strategist (human, ~3 hrs/wk)                | $900   |
| Editor-supervisor (human, ~10 hrs/wk @ $60)  | $2,400 |
| Agent infrastructure (LLM + render)          | $400   |
| Tooling (scheduling, asset CDN, etc.)        | $150   |
| **Total cost**                               | **$3,850** |
| **Gross margin**                             | **$2,650 (41%)** |

### Empire — $18,000/mo

| Cost line                                      | $/mo    |
| ---------------------------------------------- | ------- |
| Strategist (human, ~6 hrs/wk)                  | $1,800  |
| Editor-supervisor (human, ~15 hrs/wk)          | $3,600  |
| Community manager (human, ~10 hrs/wk @ $50)    | $2,000  |
| Agent infrastructure                           | $900    |
| Custom dashboard hosting                       | $200    |
| Tooling                                        | $300    |
| **Total cost**                                 | **$8,800** |
| **Gross margin**                               | **$9,200 (51%)** |

---

## Onboarding sprint margin

Onboarding is high-margin because it's mostly one-time engineering that gets templated and reused.

| Tier        | Sprint price | Engineering hours | Cost   | Margin    |
| ----------- | ------------ | ----------------- | ------ | --------- |
| Foundation  | $4,500       | ~20 hrs           | $1,500 | 67%       |
| Studio      | $9,500       | ~40 hrs           | $3,000 | 68%       |
| Empire      | $15,000      | ~60 hrs           | $4,500 | 70%       |

**The lever:** Each onboarding sprint should *reduce* the engineering hours required for the next one (templates, prompt packs, asset library schemas). Track sprint hours over time; the curve should bend down.

---

## Pass-through costs (client pays directly)

These are estimates; client picks vendors and provides keys.

| Service                     | Typical $/mo | Notes                                   |
| --------------------------- | ------------ | --------------------------------------- |
| OpenAI / Anthropic API      | $50–500      | Scales with content volume              |
| ElevenLabs (voice)          | $99–330      | Studio+ tier                            |
| Runway / Veo / Kling        | $50–500      | Studio+ tier, optional                  |
| Submagic / Captions         | $30–100      | Studio+ tier                            |
| Buffer / Publer             | $30–100      | Studio+ tier                            |
| Hosting (if custom domain)  | $20–50       | Empire tier                             |

**Total pass-through range:** $200–1,500/mo depending on tier and volume.

---

## Pricing rules (don't break)

1. **No discounts off retainer price** — only off annual prepay (the 16.6% lever above).
2. **No à la carte pricing** — full tier or no deal.
3. **Onboarding is non-negotiable** — even if a client begs to skip it, refuse. The brand voice doc and asset library are what makes the rest of delivery viable.
4. **Tool costs are always pass-through** — never bundle, never absorb. If a client wants a single invoice, charge a 15% management fee on top of pass-through.
5. **Annual price increase: 8%** — written into contract, automatic. Reflects compounding value of accumulated brand voice + analytics history.

---

## Target portfolio at steady state (Year 2)

| Tier         | Clients | MRR        | Annual revenue |
| ------------ | ------- | ---------- | -------------- |
| Foundation   | 12      | $21,600    | $259,200       |
| Studio       | 8       | $52,000    | $624,000       |
| Empire       | 3       | $54,000    | $648,000       |
| **Total**    | **23**  | **$127,600** | **$1,531,200** |

Plus onboarding revenue (~$8K avg × 15 new clients/yr = $120K).

**Target year 2 revenue: ~$1.65M.**

Headcount at steady state: founder (you) + 2 strategists + 2 editor-supervisors + 1 community manager + 1 ops/finance = 7 people. Gross margin should land around 45%.
