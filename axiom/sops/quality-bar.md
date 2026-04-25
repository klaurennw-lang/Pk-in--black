# Quality Bar

The non-negotiable standards every piece must meet before it ships. If a piece can't clear these, it doesn't ship — even if the calendar slot goes unfilled.

---

## Universal (every piece, every tier)

- [ ] Voice match score ≥85% on the voice scorer
- [ ] 0 banned phrases (per client's brand voice doc)
- [ ] All facts traceable to research brief sources
- [ ] Hook ≥4/5 on hook bank rubric
- [ ] CTA is single, concrete, action-verb based
- [ ] Length within ±10% of platform target
- [ ] No content that violates the brand voice doc's "off-limits" topics
- [ ] No content that could plausibly cause a brand crisis (use the gut-check rule below)

---

## Studio+ — production quality

- [ ] Audio: -16 LUFS ±1, -1 dB true peak max
- [ ] Captions accuracy ≥99% (sample-checked)
- [ ] B-roll cues matched within 1 frame of script timestamp
- [ ] No transitions outside the brand transition library
- [ ] Color graded with brand LUT
- [ ] All assets have valid licenses (or are generated/client-supplied)
- [ ] Thumbnail passes click-likelihood scorer ≥7/10
- [ ] Master rendered at 4K (or 1080p if 4K source not available)

---

## Per-platform format checks

### YouTube long-form
- [ ] 16:9, 1920×1080 minimum
- [ ] Chapters set
- [ ] Description includes timestamps + 3 keyword-rich sentences
- [ ] End screen template inserted
- [ ] Tags from brand library + 3 trend-relevant
- [ ] Captions: native YouTube captions enabled (do not burn in)

### YouTube Shorts / Reels / TikTok
- [ ] 9:16, 1080×1920
- [ ] Subject framed safely (no face cut-off, no lower-third covered by platform UI)
- [ ] Captions burned in (don't trust platform native on shorts)
- [ ] Hook visible/audible in first 1.2s
- [ ] Hashtag set: brand library + 3 trend, never more than 5 visible

### X video posts
- [ ] If thread, hook tweet is the standalone post; video lives in tweet 2 (or in tweet 1 with hook restated)
- [ ] Captions burned in (X caption support is poor)
- [ ] Length ≤2:20 unless premium-style long video justified

### LinkedIn
- [ ] 1920×1080 native
- [ ] Captions burned in (LinkedIn caption support is bad)
- [ ] First-line hook in post copy must work without the video

### Carousels (IG, LinkedIn)
- [ ] First slide is the hook (no cover-style intros)
- [ ] Last slide is the CTA + handle/follow prompt
- [ ] Each slide passes the squint test (legible from across the room)

---

## Empire — community + analyst quality

### Community
- [ ] Auto-reply confidence ≥0.85 on intent classification
- [ ] 0 unauthorized commitments made on behalf of client
- [ ] 0 troll engagements
- [ ] Lead capture: 100% to CRM

### Analyst
- [ ] Every claim cites a number with a source
- [ ] Statistical claims include sample size or confidence
- [ ] Recommendations are specific, actionable, measurable
- [ ] Report ≤2 pages

---

## The gut-check rule

Before any piece ships, a human asks: **"If this went viral for the worst possible reason, would the client be okay?"**

If the answer is "probably not," the piece doesn't ship until edited. If still no after edit, the piece is killed. Better an empty calendar slot than a brand crisis.

---

## Review gates

Every piece passes through review gates before publishing:

```
Strategist (auto)
  └─> human strategist (weekly approval)
       └─> Researcher (auto)
            └─> Scriptwriter (auto)
                 └─> human scriptwriter spot-check (per-piece if voice score 70-85, skip if >85)
                      └─> Producer (auto)
                           └─> Editor (auto)
                                └─> human editor-supervisor (per-piece, mandatory)
                                     └─> Distributor (auto)
                                          └─> auto-publish
```

Empire community: auto-classify → auto-reply (low-risk only) → human (escalations).

Empire analyst: auto-generate → human review before sending to client (Sunday 8:30pm window).

---

## What "kill" means

Killing a piece is not failure. It's quality control working.

- Piece is removed from calendar
- Reason logged in `decision-log.md`
- Pattern tracked: if same kind of piece keeps getting killed, prompts/process need updating
- No charge to the client (kills are part of the retainer)

Target kill rate: 5–10% of generated pieces. Lower means the bar is too soft. Higher means the upstream agents need tuning.

---

## What "revise" means

- Single revision: agent re-runs that step with feedback. Common.
- Two revisions: review the prompt or the input. Probably an upstream issue.
- Three revisions: kill the piece. Continuing wastes more time than starting over.

---

## When to break the quality bar

Never. The whole pricing model is built on consistency. If we break the bar to hit a deadline once, the next time becomes easier to break, and the client noticed every shipped piece dropped a notch.

If the calendar can't be filled at quality bar, the calendar is wrong. Adjust cadence with the client. Don't ship slop.
