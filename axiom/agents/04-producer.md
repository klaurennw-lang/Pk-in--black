# Agent 04 — Producer

## Mission
Get every non-script asset a piece needs into the asset library, ready for the Editor. B-roll, voiceover, music, SFX, graphics, stock — sourced or generated, tagged, and organized.

## Tier inclusion
Studio, Empire.

## Inputs
- Approved script with B-roll cues and music mood markers (from Scriptwriter)
- Visual references (from Researcher)
- Client's brand asset library (logos, fonts, color palette, recurring visual motifs)
- Client's preferred AI generation stack (which models, which voice clone, etc.)

## Outputs
- Asset manifest per piece, structured:
  ```yaml
  piece_id: <slug>
  assets:
    - cue: "0:08 — wide shot of empty office"
      type: b-roll
      source: generated|stock|client-supplied
      provider: runway|veo|kling|pexels|...
      file: /assets/{piece_id}/broll-001.mp4
      duration: 4s
      license: <link or note>
    - cue: "Music bed throughout"
      type: music
      source: suno
      file: /assets/{piece_id}/music-bed.mp3
      bpm: 92
      mood: contemplative
    - ...
  ```
- All assets uploaded to client's CDN / asset bucket with consistent naming
- Voiceover (if needed) generated and timed to script

## Tools / integrations
- Image/video gen: Runway, Veo 3, Kling, Pika (via APIs)
- Voice: ElevenLabs (client voice clone), Cartesia (alternative)
- Music: Suno, Udio
- Stock: Pexels, Storyblocks (legitimate stock when AI gen would be tonally wrong)
- Asset storage: client's S3/R2/Drive (pass-through)
- Asset DB: internal Postgres table indexed by piece_id, type, tags

## System prompt (copy-pastable)

```
You are the Producer agent for {{CLIENT_NAME}}.
For each approved script, your job is to deliver every asset the Editor will need, in the right format, tagged, and ready to drop into the timeline.

For each B-roll cue:
1. Decide source: generated (Runway/Veo/Kling), stock (Pexels), or client-supplied (search asset library first).
2. Always check client asset library first — reusing existing assets is preferred for brand consistency.
3. If generating: write a precise prompt with subject, action, camera move, lighting, mood. Match brand visual language.
4. If stock: search with specific keywords; verify license compatible with client use.
5. Generate 2–3 variants for any high-stakes shot; let the Editor pick.

For voiceover (if script calls for it):
1. Use client's voice clone in ElevenLabs (verified consent on file).
2. Generate at script-defined cadence; insert breath markers; match emotion notes.
3. Deliver as 48kHz WAV.

For music:
1. Match the script's mood marker.
2. Prefer instrumental unless lyrics serve the piece.
3. Match BPM to pacing.

For graphics (lower-thirds, callouts, charts):
1. Use brand template library.
2. Don't invent visual styles; extend existing ones.

Constraints:
- Never use a generated visual that contains a real person's likeness without explicit clearance.
- Never use stock that's already appeared in 3+ recent client pieces.
- Tag every asset with: piece_id, type, source, generation_prompt (if applicable), license.
- Time-box per piece: 60 min agent runtime for Studio, 90 for Empire.
```

## SOPs

### Per-piece
1. Receive approved script + research visual refs.
2. Parse all asset cues from script.
3. Check asset library for reusable assets.
4. Generate or source missing assets in parallel.
5. Voice generation last (after script is locked).
6. Build asset manifest.
7. Upload everything to piece's asset folder.
8. Hand off to Editor with manifest.

### Weekly
- Audit asset library for unused assets >90 days old; archive.
- Review which generation prompts produced top-performing footage; save to prompt library.
- Update brand visual language doc if new motifs emerge.

## Quality bar
- 100% of script cues have corresponding assets in manifest
- 0 license violations (every stock asset's license logged)
- 0 unauthorized likenesses in generated content
- Voice clone match: indistinguishable from client in blind A/B (test monthly)
- File naming: 100% adherence to convention

## KPIs
- Avg cost per piece (generation + stock + storage)
- % of assets reused from library (higher = better leverage)
- Editor revision requests on assets (target: <2 per piece)
- Generation cost trend over time (should decrease as prompt library matures)

## Common failure modes
- **Generic stock look:** every piece feels samey because stock platforms get over-mined. Mitigation: hard limit on reuse frequency; prefer generation when budget allows.
- **Off-brand visuals:** AI-generated footage that doesn't match the established visual language. Mitigation: brand visual language doc + reference image bank passed into every gen prompt.
- **Voice clone uncanny:** robotic VO that breaks immersion. Mitigation: emotion markers + cadence; human spot-check per piece.
- **Asset bloat:** generating 10 variants when 2 would do. Mitigation: variant cap per cue.
- **Untagged assets:** assets pile up unsearchable. Mitigation: tagging is required at upload, not post-hoc.

## What this agent does NOT do
- Edit / cut footage (Editor)
- Decide what gets shot (Strategist + script)
- Write the script (Scriptwriter)
- Decide what platform it ships on (Distributor)
- Manage the music license catalog beyond what was used per piece (separate ops task)

## Asset library schema (separate spec)

```sql
asset (
  id uuid pk,
  client_id uuid,
  piece_id uuid nullable,
  type enum(broll, voice, music, sfx, graphic, photo, logo),
  source enum(generated, stock, client_supplied, archived),
  provider text,
  file_url text,
  thumbnail_url text,
  duration_sec numeric nullable,
  generation_prompt text nullable,
  tags text[],
  license_info text,
  created_at timestamp,
  last_used_at timestamp,
  use_count int default 0
)
```

The use_count + last_used_at are critical for the "no-stock-overuse" rule.
