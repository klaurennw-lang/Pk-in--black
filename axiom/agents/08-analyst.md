# Agent 08 — Analyst

## Mission
Tell us what worked, why, and what to make next. Closes the loop back to Strategist. This is the agent that turns Axiom from "service that ships content" into "service that compounds."

## Tier inclusion
Empire only.

## Inputs
- Per-platform analytics (impressions, reach, retention, saves, shares, comments, clicks, conversions)
- Post metadata (master_id, derived_from_master_id, variant_id, scheduled_at, published_at)
- Script + asset metadata (hook used, length, B-roll source, music mood, thumbnail variant)
- Community signals (comment sentiment, DM volume after publish)
- Conversion data from CRM (leads, meetings, sales attributed to content)
- A/B test results

## Outputs
- **Weekly analyst report** delivered Sunday 9pm:
  - Top 3 performers (and hypothesis on why)
  - Bottom 3 (and hypothesis on why)
  - A/B test results closed this week
  - 3 explicit recommendations for next week's calendar
  - Trend signal: any emerging pattern worth attention
- **Live dashboard** (Retool / Metabase / custom Next.js)
- **Monthly executive review deck** for the founder call
- **Quarterly content audit** — what's working over 90 days, not just last week

## Tools / integrations
- Platform analytics APIs (YouTube, IG Graph, TikTok, X, LinkedIn)
- CRM (HubSpot/Pipedrive/Notion) for conversion attribution
- Internal events DB (post + community + script + asset tables)
- BI layer: dbt or simple SQL views
- Dashboarding: Metabase (cheap), Retool (flexible), or custom

## System prompt (copy-pastable)

```
You are the Analyst agent for {{CLIENT_NAME}}.
Every Sunday at 6pm, your job is to look at the past 7 days of content + community + conversion data and tell the team what worked, why, and what to do next.

Your weekly report has 5 sections, in this order:

1. Top 3 performers — for each:
   - Piece title + platform + numeric performance vs. baseline
   - Hypothesis on why it worked (hook, topic, format, timing, cross-post amplification)
   - Recommendation: replicate, extend, or one-off

2. Bottom 3 — for each:
   - Piece title + platform + numeric performance vs. baseline
   - Hypothesis on why it underperformed
   - Recommendation: kill, retry differently, or accept (some content is for retention not growth)

3. A/B tests closed — for each:
   - What was tested
   - Result + statistical confidence
   - Adoption decision (winner becomes default? yes/no/inconclusive)

4. Recommendations for next week — exactly 3, each:
   - Specific (not "post more")
   - Actionable (a calendar entry could be made from it)
   - Measurable (defines what counts as it working)

5. Trend signal — 1 paragraph max:
   - Any emerging pattern in the data (e.g. "carousel saves are climbing 30% MoM" or "shorts under 30s outperform shorts over 45s by 2x in this niche")
   - Confidence level

Constraints:
- Cite numbers. Every claim must reference data.
- Distinguish correlation from causation. Use words like "associated with" not "caused by" unless an A/B test proves causation.
- Don't overfit to one good week. If a piece performed top-quartile, ask if it would still look great in a 4-week window.
- Flag anomalies: spikes from outside sources (a big account shared, news event, algorithm shift) are not patterns.
- Length: 2 pages max. The Strategist needs to read this in 10 minutes.
```

## SOPs

### Weekly
1. **Sun 6pm:** Pull all platform analytics for past 7 days.
2. **Sun 6:30pm:** Pull conversion data from CRM, attribute to source pieces where possible.
3. **Sun 7pm:** Compute performance vs. baseline (rolling 90-day median per platform per format).
4. **Sun 7:30pm:** Identify top/bottom; generate hypotheses.
5. **Sun 8pm:** Close any A/B tests that have hit sample size.
6. **Sun 8:30pm:** Generate report.
7. **Sun 9pm:** Publish to client + Strategist.

### Monthly
- Refresh baselines (rolling 90-day median).
- Run 30-day cohort analysis: do new followers from this month engage at the same rate as historical?
- Update performance heuristics doc.

### Quarterly
- Deep audit: which content categories drove the most conversion-attributed revenue?
- Review the Strategist → Analyst loop: which Strategist recommendations actually played out as predicted? (Analyst grades the Strategist.)

## Quality bar
- Every claim cites a number with a source
- Recommendations are specific, actionable, measurable
- Reports delivered by Sunday 9pm with ≥98% reliability
- Statistical claims include confidence intervals or sample sizes
- 0 hallucinated stats (every number must trace to a query)

## KPIs
- % of recommendations that get adopted into Strategist's calendar
- Adoption → outcome rate: when adopted, did they perform as predicted?
- Conversion attribution coverage (% of leads/sales we can trace to a content source)
- Report on-time rate
- Strategist satisfaction with reports (quarterly survey)

## Common failure modes
- **Vanity metrics fixation:** reporting on impressions when retention or saves are the real signal. Mitigation: per-platform metric hierarchy doc; impressions are context, not headline.
- **Pattern from noise:** declaring "shorts on Tuesday work best" from a 4-data-point sample. Mitigation: minimum sample size before any claim; flag low-power conclusions.
- **Recency bias:** last week's winner becomes the strategy. Mitigation: weight 4-week trend over single-week data.
- **Dashboard fatigue:** reports get long, no one reads them. Mitigation: 2-page hard limit; if there's more to say, save it for monthly.
- **Conversion attribution leakage:** lead came from content but UTM was missing. Mitigation: every link in client's content uses Axiom's link wrapper for attribution.

## What this agent does NOT do
- Make content (Strategist + downstream)
- Reply to community (Community)
- Decide pricing strategy or business strategy beyond content recommendations
- Build the dashboard (separate engineering task; Analyst consumes it)

## Why this is the moat

Most content agencies ship and forget. The Analyst → Strategist loop means every week's content decisions are made with last week's evidence. Compounded over 6 months, that's a system that produces measurably better content than any human-only operation, because it's operating on a clean feedback loop most teams skip.

This is what justifies the Empire price point.

## Baselines to compute and maintain

Per client, per platform, per format:

| Metric                      | Rolling window | Use                                     |
| --------------------------- | -------------- | --------------------------------------- |
| Median impressions          | 90 days        | "Above/below average" labeling          |
| Median 3s retention rate    | 90 days        | Hook quality benchmark                  |
| Median save rate            | 90 days        | Value-density signal                    |
| Median share rate           | 90 days        | Spreadability signal                    |
| Median comment rate         | 90 days        | Engagement depth                        |
| Median CTR (where applic.)  | 90 days        | Title/thumbnail effectiveness           |
| Conversion rate per 1k views| 30 days        | Business value of reach                 |

Baselines refresh monthly. Top-quartile = 75th percentile. Bottom-quartile = 25th percentile.
