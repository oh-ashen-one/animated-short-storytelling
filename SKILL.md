---
name: animated-short-storytelling
description: |
  Produce short animated films (30s–5min) with AI video models. Covers the full
  pipeline: concept, style anchors, character sheets, shot lists, per-shot
  generation, cost budgeting, and assembly. Use when: "make an animated short",
  "anime video", "animated story", "AI film", "shot list for animation",
  "character consistency across clips", "voiceover-driven video".
---

# Animated Short Storytelling

A production workflow for making coherent animated shorts from text-to-video models. Built from real productions; every hard-won lesson is in `LEARNINGS.md` — read it before spending money.

## Golden rules

1. **Never raw-dog text-to-video for a multi-shot film.** Character and style will drift between clips. Always anchor with a character sheet and a locked style suffix (see below).
2. **Plan the budget before generating.** Video models charge per second. Do the math first, keep a retake buffer, and test cheap before committing.
3. **One narration/story beat per shot.** If a shot carries two beats, split it or simplify it.
4. **Simple camera moves.** Static, slow push-in, slow pull-back, gentle drift. Fast/zooming moves are where face-morphing and ghosting artifacts live.
5. **Log everything.** Model, prompt, duration, cost, verdict (good/bad + why). That log is what makes the next film cheaper and better.

## Workflow

### Phase 1 — Concept & constraints

- Nail the logline (one sentence), target runtime, and aspect ratio. **Aspect ratio is a day-one decision** — confirm the delivery platform (vertical 9:16 for social vs horizontal 16:9) before ANY generation; a wrong-aspect take is a wasted take.
- Runtime math: clips have a max duration (e.g. 15s). A 60s film at 10s/shot = 6 shots. Shorter runtimes force better films — cut filler beats, not retake budget.
- Dialogue-driven or VO-driven? For VO-driven films, generated audio is irrelevant — never spend effort on it; the VO + music go on in the edit. **Write the VO lines first and size shots to them: one spoken line ≈ 5–6s, so default to 5–6s shots.** Longer shots under a single line create dead air.

### Phase 2 — Style anchors (cheap tests before real spend)

- Generate 2–4 short test clips (5s is enough) of the SAME simple scene in candidate styles. One scene, one variable (style), fair comparison.
- Watch them. Pick ONE anchor. Kill the rest. A style that "blends" two anchors usually differentiates poorly — prefer a single strong identity.
- **Nostalgia is a first-class selection criterion.** Between two working styles, pick the one with nostalgic pull (retro cel, VHS, low-poly game graphics, film grain) over the one that's merely pretty. Note: Ghibli-painterly tests beautiful but is overused and reads generic, not nostalgic — avoid as a default.
- Write the winning style as a **style suffix** — a fixed string appended verbatim to every shot prompt. Example that tested well:
  `1990s retro anime style, cel shaded animation, film grain, vintage anime aesthetic`

### Phase 3 — Character sheet

- Generate a character reference sheet with an image model BEFORE any film shots: full-body front/side/back turnaround + face close-up + palette, plain background.
- Lock a simple, distinctive outfit in the sheet prompt (specific colors). Every later prompt references the same outfit words.
- Pass the sheet as an image reference on EVERY shot (`--image <sheet>` with the Higgsfield CLI). Verified: keeps the character on-model across shots.
- Do NOT use the sheet as a start/frame image — it's a reference, not a first frame. If a shot needs a specific first frame, generate a dedicated keyframe image for that shot.

### Phase 4 — Shot list

For each shot, write: number, timecode, story beat, one-sentence action, camera move (keep it simple), and the final generation prompt (scene description + style suffix). Repeat set/location descriptions word-for-word between shots sharing a location.

### Phase 5 — Generate

- Fire shots individually or in small parallel batches; review each before generating the next. A wrong vibe in shot 1 poisons the whole film.
- Regenerate weak shots immediately — that's what the buffer is for. Don't "fix it in the edit."
- Download and keep every keeper with a strict naming scheme: `shot-01.mp4`, `shot-02.mp4`, ...

### Phase 6 — Assemble

- Concatenate in an editor (or ffmpeg), lay VO and music, color/level pass, done.
- Trim to target runtime in the edit; generating exact durations to the frame is not worth the effort.

## Model reference — Higgsfield CLI

Install: `npm i -g @higgsfield/cli`, auth: `higgsfield auth login`, then select a billing workspace first (`higgsfield workspace list` / `workspace set <id>`) — cost and generate calls fail without one.

### MiniMax H3 (`minimax_h3`) — anime-capable video

- Resolution: **2K only**. Aspect ratios: auto, 21:9, 16:9, 4:3, 1:1, 3:4, 9:16.
- Duration: integer seconds, **5–15** usable (schema says ≥4 but a 4s batch failed 3/3 server-side while 5s+ succeeded — avoid 4).
- Cost: **4 credits/sec** at 16:9 2K (10s = 40, 15s = 60). Failed jobs are NOT charged.
- Media inputs: `--image` (reference), `--start-image`, `--end-image`, reference arrays. A character sheet passed via `--image` keeps the character consistent.
- Discovery: `higgsfield model get minimax_h3 --json`. The schema omits min/max for duration — probe limits with `higgsfield generate cost <model> --duration N` (free) instead of burning a generation.
- Generate: `higgsfield generate create minimax_h3 --prompt "..." --image sheet.png --duration 10 --aspect_ratio 16:9 --resolution 2K --wait --wait-timeout 20m`

### Nano Banana 2 (`nano_banana_2`) — character sheets / reference images

- Produces excellent production-style turnaround sheets (front/side/back + portrait + palette swatches) from a single prompt. Occasional transient HTTP 503 — just retry.

## Prompting patterns that tested well

- Structure: `[scene + action + mood + camera move]. [style suffix]`
- Name the character the same way every time ("a young boy in a yellow t-shirt...") even with a sheet attached — belt and suspenders.
- Mood words do heavy lifting in dialogue-free films: "melancholic", "lonely", "bittersweet".
- Ending a shot "on" something (a face, an object) gives the edit a clean cut point.

## Evolving this skill

After every session: append dated entries to `LEARNINGS.md` (model, cost, verdict, lesson). Fold workflow-changing lessons back into this file. Never log private info — no account identifiers, workspace IDs, job URLs, tokens, or absolute personal paths.
