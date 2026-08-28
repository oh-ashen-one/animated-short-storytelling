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

1. **Never generate without explicit director confirmation.** Quote the cost first, wait for a green light. (Director rule, 2026-08-19.) Style/vibe tests are ALWAYS the minimum duration — 4s on the direct API — never longer.
2. **Never pre-judge takes.** Download everything and present it all — the director judges the footage together with you, on the actual files. Don't filter or rank before he watches. (Director rule, 2026-08-20.)
3. **Never raw-dog text-to-video for a multi-shot film.** Character and style will drift between clips. Always anchor with a character sheet and a locked style suffix (see below).
4. **Plan the budget before generating.** Video models charge per second. Do the math first, keep a retake buffer, and test cheap before committing.
5. **Every on-screen human is cast as a recognizable famous figure** (movie, TV, anime, game, historical — anything that stops the scroll). One anchor per episode (e.g. Hank Hill, Batman). **Describe the likeness, never name the celebrity** — the image and video models IP-check named people and reject or deface them; "a middle-aged Texas propane-salesman type with a mustache and a white shirt" gets through, the name doesn't. Each recurring cast member gets their own same-style char sheet; background faces stay silhouettes.
6. **One narration/story beat per shot.** If a shot carries two beats, split it or simplify it.
7. **Simple camera moves** for VO/mythic films: locked-off, slow push-in, slow pull-back, gentle drift. Fast/zooming moves are where face-morphing and ghosting artifacts live. **Exception — Office argument singles:** FRAME ZERO is already a quick whip pan onto the face, then a short zoom, then settle. A still start was a director reject.
8. **As little on-screen text as possible — and what exists must be static.** Small fonts, counters, and UI chrome are the #1 AI-slop tell: numbers that increment, spin, or tick ("like counter climbs past 40,000") render as garbled morphing slop. Rules for screen-within-screen: ONE short headline max, large font, static for the whole take (it may slowly pulse/glow — "emanate, not increment"); never counters, tickers, notification badges, or body text; keep the screen de-emphasized (over-shoulder, low in frame) with focus on the person/environment instead of a macro of the display. Any "engagement goes up" beat must be carried by performance and framing (face, glow, posture), never by UI motion. (Director rule, 2026-08-19, after a rejected take.)
9. **Episodes must be creatively distinct.** Not just a new script — a new TOPIC, world, cast, and emotional register. Ep1 and Ep2 were both "addictive algorithms" with the same kid, same locations, same melancholy; the director's verdict: "way too similar — we have the entire world of creativity." Recurring style/character lore is a seasoning, not the meal. When pitching episode ideas, explicitly check the pitch against every previous episode's topic and theme; anything in the same thematic neighborhood gets reworked or cut. (Director rule, 2026-08-19.)
10. **Exploit the medium — go mythical/surreal when the shot allows it.** We are not bound to documentary realism: if a shot (especially a closer) can carry an impossible image — data-fireflies rising off wet lawns, a sky-whale, frozen glass water — prefer it over a "normal human thing." One mythic element per shot, anchored in the scene's reality, never a random fantasy pile-on. Put it FIRST and BIG in the prompt — as one clause in a long prompt H3 sheds it and it never renders. And keep it SUBTLE on screen (director on the sky-whale take: "more subtle next time"). (Director rule, 2026-08-19.)
11. **Log everything.** Model, prompt, duration, cost, verdict (good/bad + why). That log is what makes the next film cheaper and better.
12. **Official MiniMax API only, 768P only.** All video generation is MiniMax-H3 via MiniMax's own pay-as-you-go API (`https://api.minimax.io`) only. Never Higgsfield or any reseller for video. Never 2K, never H3-Regenerate-2K. Direct API is $0.08/sec at 768P vs $0.13/sec at 2K vs ~$0.19–0.20/sec on Higgsfield. Prompt enhancement and optional Context-IR are OK if vibe/intent stay the same. Key is env `MINIMAX_API_KEY` (pay-as-you-go). Never commit it. Do not offer 2K as an option.

## Workflow

### Phase 1 — Concept & constraints

- Nail the logline (one sentence), target runtime, and aspect ratio. **Aspect ratio is a day-one decision** — confirm the delivery platform (vertical 9:16 for social vs horizontal 16:9) before ANY generation; a wrong-aspect take is a wasted take.
- Runtime math: clips have a max duration (e.g. 15s). A 60s film at 10s/shot = 6 shots. Shorter runtimes force better films — cut filler beats, not retake budget.
- Dialogue-driven or VO-driven? For VO-driven films, generated audio is irrelevant — never spend effort on it; the VO + music go on in the edit. **Write the VO lines first and size shots to them: one spoken line ≈ 5–6s, so default to 5–6s shots.** Longer shots under a single line create dead air.

### Phase 2 — Style anchors (cheap tests before real spend)

- Generate 2–4 short test clips (5s is enough) of the SAME simple scene in candidate styles. One scene, one variable (style), fair comparison.
- Watch them. Pick ONE anchor. Kill the rest. A style that "blends" two anchors usually differentiates poorly — prefer a single strong identity.
- **Nostalgia is a first-class selection criterion.** Between two working styles, pick the one with nostalgic pull (retro cel, VHS, low-poly game graphics, film grain) over the one that's merely pretty. Note: Ghibli-painterly tests beautiful but is overused and reads generic, not nostalgic — avoid as a default.
- **H3 carries painterly environments, not anime faces.** Humans rendered in anime/watercolor styles read as AI slop; the SAME styles' environment-only shots (night car wash, golf course) tested "fire" with the director. Keep humans in the retro-game family (low-poly 3D); reserve painterly styles for environment shots. (2026-08-19 style trials.)
- **A style can execute correctly and still be wrong for the project.** Style selection is taste, not correctness — that's why anchors are tested cheap (5s) before any real shots.
- **Style intensity = texture-level instructions, not era labels.** Mild suffixes ("1990s retro anime style, film grain") drift back to the model's polished default, especially in dark interiors. Push retro HARD and concretely: ink lines, dust and scratches, frame-rate feel, palette fade.
- **Don't build a film's identity on artifacts the model won't reliably produce.** Analog-artifact keywords ("scan lines", "VHS tracking distortion") were ignored by MiniMax H3 in testing — the clip came out clean and modern. Test the artifact, not just the scene.
- Write the winning style as a **style suffix** — a fixed string appended verbatim to every shot prompt. Examples that tested well:
  - `1990s retro anime style, cel shaded animation, film grain, vintage anime aesthetic`
  - `Early 2000s PS2 era video game graphics, GTA style low poly 3D, flat muddy textures, jagged aliased edges, muted gray-brown color grading, foggy draw distance, RenderWare aesthetic` ← strongest nostalgia anchor found to date
  - `mid-2000s early HD era video game graphics, GTA IV era low poly 3D, desaturated brown-gray color grading, harsh bloom lighting, baked-in shadows, plasticky specular sheen, slight motion blur` ← Ep3 anchor ("PS3"). The whole retro-game family tested strong: PS1 (dither/jitter), N64 (blur/fog), PS3/GTA-IV, prerendered survival-horror (slightly meh — blocky heads).

### Phase 3 — Character sheet

- Generate a character reference sheet with an image model BEFORE any film shots: full-body front/side/back turnaround + face close-up + palette, plain background.
- **One sheet per STYLE, not per film.** If the style anchor changes medium (2D cel → 3D low-poly), regenerate the sheet in the new medium. A 2D sheet anchoring 3D shots is untested and likely counterproductive.
- **Age-drift guard:** models age characters up by default. If the character is a child, prompt it explicitly in the sheet AND every shot: "young kid proportions, oversized head, short stature". Verified fix for a grown-man-reading character in low-poly 3D.
- Lock a simple, distinctive outfit in the sheet prompt (specific colors). Every later prompt references the same outfit words.
- Pass the sheet as an image reference on EVERY shot (`--ref <sheet>` on `h3.sh` / the official MiniMax API). Verified: keeps the character on-model across shots. Note: sheet-referenced shots drift slightly cleaner/smoother than the raw style test — if you want maximum grit, push the texture words harder when a sheet is attached.
- Do NOT use the sheet as a start/frame image — it's a reference, not a first frame. If a shot needs a specific first frame, generate a dedicated keyframe image for that shot.
- **Age arcs: one sheet per AGE, same outfit.** A character who is a kid in early shots and an adult later gets two sheets (kid proportions + adult proportions) in the same style with identical outfit colors and one carryover feature (e.g. round glasses). The match-cut between the last kid shot and the first adult shot sells the years. (Verified in Ep4 — zero drift across the age jump.)

### Phase 4 — Shot list

For each shot, write: number, timecode, story beat, one-sentence action, camera move (keep it simple), and the final generation prompt (scene description + style suffix). Repeat set/location descriptions word-for-word between shots sharing a location.

**Presenting the script to the director (his rule, 2026-08-20):** he records the VO himself — never present the script as written prose. Show each shot as a one-liner of what the viewer SEES (summarized look, not the full prompt); suggested VO lines go BELOW the shot list, clearly marked as suggestions.

### Phase 5 — Generate

- Fire shots individually or in small parallel batches; review each before generating the next. A wrong vibe in shot 1 poisons the whole film.
- **ffprobe the FIRST downloaded file of every batch** against the intended delivery frame (resolution + aspect) before firing the rest — a cheap probe catches systemic wrapper/ratio bugs before they waste a whole batch. (Ep3: three 16:9 takes before anyone checked.)
- **Style varies seed to seed.** Identical prompt + suffix on a new seed can come back visibly softer ("looks PS2 not PS3"). Budget retakes on hero shots; a re-roll is often all it takes.
- **4s shots are the right unit for inventory montages** (fast-fashion rack, almond rows, golf sprinklers...): ~6 montage items ≈ 24–28s of VO room.
- **Pass prompts from files, not inline** — `--prompt "$(cat .prompt-NN.txt)"`. Apostrophes/em-dashes in inline prompts can break the shell mid-batch (the job survives; your wait loop doesn't).
- **Screen-within-screen works on H3** (verified 3/3 first-take in Ep2): write the screen's content explicitly ("the phone screen clearly shows three spinning slot machine reels") and keep the camera to one slow move.
- Failed jobs may show a partial charge followed by a refund minutes later — tally net from the ledger at close, never mid-run balances.
- Regenerate weak shots immediately — that's what the buffer is for. Don't "fix it in the edit."
- **Judge on early AND late frames.** A time-locked action ("the patterns light up") may only complete in the final second — a mid-clip frame can look like a failed take and trick you into an unneeded retake. (Ep4 shot 7: one brain-scan pattern at 2.5s, both matching by 4.5s.)
- **Artifact tolerance:** a short (~2s), non-narrative-breaking artifact on an otherwise strong take is keepable. Cap retakes per shot (3 max), keep the best, flag it, and offer the director one priced retake after they watch the file — don't burn budget chasing perfection unprompted.
- Download and keep every keeper with a strict naming scheme: `shot-01.mp4`, `shot-02.mp4`, ...
- **Dialogue shorts: send the mp4 the moment a job succeeds.** Do not wait for lmk / ?. Concat keepers in a later pass.

### Phase 6 — Assemble

- Concatenate in an editor (or ffmpeg), lay VO and music, color/level pass, done.
- Trim to target runtime in the edit; generating exact durations to the frame is not worth the effort.
- **CapCut rejects symlinks** ("not accessible" on import). Delivery/film-cut folders must be REAL file copies — bytes are cheap; copy, don't link.
- **Soundtrack: always deliver ONE Suno prompt alongside the film, not per-shot.** The score is a single fluid piece for the whole runtime — per-shot music is choppy and pointless under VO. Write the prompt to the film's emotional thesis (for melancholic tech-commentary: detuned music box / nostalgic-video-game-menu-wrong / tape hiss / no drums / no drops / instrumental). Tell the director to toggle Instrumental in Suno explicitly and generate 2–3 takes — Suno over-decorates long tracks.

### Phase 7 — Packaging for social (from a 40-reel teardown of a top AI-satire account)

The film isn't done when it's assembled — package it for the feed:
- **Frame-1 premise card:** state the entire premise as huge centered white text at 0:00 ("how kids experience 8pm now"). No cold open. Instant comprehension = no swipe.
- **Fragment-per-shot captions:** 2–5 words per shot, synced to the VO. The reel must work muted — the text IS the narration for muted viewers.
- **Cut rhythm:** top accounts cut every ~1.7s. For melancholy films hold shots longer (2.5–5s) but keep the TEXT changing within the shot.
- **Escalation arc:** ordinary → progressively surreal. Even a sad film escalates.
- **Deadpan tonal contrast:** let the sadness sit under flat narration. Never wink.
- **Longer reels overperform** for this format (≥50s beats <50s). 60s is a feature, not a risk.
- **Recurring signature:** one recurring element per film (a sound motif, an object, a card) — serialized universes reward follows. No hashtags, no CTAs in the caption.

### Phase 8 — Public process breakdown (Notion)

When a film wraps, ship a public "how I made it" page on Notion. The community post IS part of the deliverable — don't wait to be asked.

- **Structure:** what the film is → tools used → style recipe (suffix verbatim) → character sheet (prompt + image) → every shot in order with its verbatim prompt in a code block and the output video embedded directly under it → score prompt + playable audio → the full rough cut embedded → numbers (shot count, credits spent, failures) → one big-lesson callout.
- **Recover exact prompts from generation history, never from memory or chat:** `higgsfield generate list --json`, then `higgsfield generate get <id> --json` → `params.prompt`. Match jobs to local shot files by byte size (`curl -sI <result_url>` content-length vs local file size) — job names and timestamps will not map to `shot-NN.mp4` on their own.
- **Hosting is free:** generation `result_url`s are public CDN links — embed them directly. The assembled rough cut has no URL; upload it with `higgsfield upload create <file>` and embed the returned URL.
- **Notion markdown:** `<video src="URL">caption</video>`, `<audio src="URL">caption</audio>`, `![caption](URL)` for images; prompts in fenced code blocks (no escaping needed inside code blocks).
- **Publishing is manual:** the API can create the page but cannot flip it public — end by telling the director to hit Share → Publish.


## Office mockumentary (H3 live-action, locked 2026-08-28)

A second tested genre besides the retro-game VO films. 9:16 talking-head / A-roll argument shorts with native H3 speech. Reproduce this grammar exactly.

**Coverage:** one character per generation. Never two faces in one clip — two-shots cloned faces, went generic, and both people looked like the same man. Singles in the SAME office world, different rooms. Concat in ffmpeg later.

**Locations:** Michael = regional manager's private office (not reception). Dwight = HIS salesman cubicle/desk (not reception, not Michael's office). Spell the room in SETTING and negative-prompt the other room (no TEAMWORK poster / sage-green counter / World's Best Boss mug on Dwight's desk).

**Camera (argument singles):** FRAME ZERO is already in motion. First frame is a QUICK WHIP PAN onto the face, then a short zoom-in, then settle after ~1s. Never a still lock that starts moving later. Then slight handheld documentary. Do not 360. Do not cut inside the generation. This is an exception to golden rule 7 (simple/slow camera) — the whip is the show's coverage, not a stacked move.

**Eyeline:** Dwight looks camera-left, Michael camera-right, at an unseen coworker.

**Performance:** SLOW. Passion, not anger, not speed. Pause between sentences. Fill 8–10s. Chipmunk / scream / Andy Bernard tenor is a reject. Prompt: Clear. Every word. Do NOT moan. Do NOT swallow words. Full conversational sentences, not a grunt then a punchline.

**Voice lock (prompt every take):** Dwight is dry, nasal, intense, clipped, slightly formal, flat midwestern — NOT theatrical, musical, bright tenor, singing, or high-pitched. Michael is Michael Gary Scott, not Andy Bernard.

**Dialogue:** overlapping real conversation ("Oh shit", "Bro"), nerdy, specific leaderboard numbers. Name-drop ONE comparison in the moment, not every benchmark in one breath. Not essays, captions, or press-release. Each later Dwight clip needs NEW information.

**Spoken numbers as full words.** H3 reads "262k" as "two sixty two" and "512" as digit groups. Write "two hundred sixty two thousand" and "five hundred twelve gigabyte" inside `<d>[English] ...</d>`. Never dump a pile of numerals.

**Identity:** director-supplied stills as `role=reference_image`. Describe wardrobe/hair/glasses AND attach the still. CAST LOCK: EXACTLY ONE PERSON, no extras, no clones, adult scale. Jim Halpert is NOT locked from episode screenshots — do not reshoot Jim-led until better stills. Named celebrity close-ups can 1027 `output new_sensitive`.

**Confirm before generate:** spoken-line script + every ref image + cost (~$0.80 per 10s). Do not paraphrase locked lines. When Jim was recast as Michael, Michael says Jim's lines word for word.

**Delivery:** send each mp4 the moment the job succeeds. Do not wait to be pinged. Concat keepers later.

**Confessionals:** v5 talking-head is the gold (off-camera interviewer, dry, slow). 15s Office structure if used: 5s fight → 5s confessional → 5s fight.

**Stills:** H3 is video. MiniMax image-01 from a tight MCU headshot blows the head into a bobblehead. Hypebeast stills were killed.

**Title-plate overlay (Ghost of Tsushima test, same session):** locked-tripod ambient loop; overlay menu text from frame 0 with no fade; text only, no left-side darkness/scrim. A "more PS5" grade of the 768p source was rejected.

## Model reference — MiniMax direct API (ALL video gen, 768P standard)

**House rule (director, 2026-08-27): every video generation is MiniMax-H3 via the official MiniMax API (`https://api.minimax.io`) at 768P. No Higgsfield video. No 2K. No H3-Regenerate-2K. No photoreal 2K override.** Prompt enhancement and optional Context-IR are OK if vibe/intent stay the same. Direct API is **$0.08/sec at 768P** vs $0.13/sec at 2K vs ~$0.19–0.20/sec on Higgsfield. Reference images: first 5 free per generation, $0.04 each after. Key is env `MINIMAX_API_KEY` (pay-as-you-go). Never commit it. Token Plan subscriptions and prepaid Credits do NOT cover H3 video. Note: 768P vertical renders 768×1344 (7:4, ~2% wider than 9:16) — crop/pad at assembly.

Wrapper: `~/shorts-factory/h3.sh` (submit → poll → download, bash + curl + python3):

- `h3.sh gen --prompt-file .prompt-01.txt --out shot-01.mp4 --duration 5 --ratio 9:16 --ref <sheet>` — resolution is locked to 768P.
- `--ref` / `--first-frame` / `--last-frame` accept a local path (auto-uploaded), an `mm_file://<file_id>`, or an https URL. Character sheets go in as `role=reference_image`.
- `h3.sh upload <file>` → prints a `file_id` (uploads valid 7 days, image sides 256–5760px). Reference as `mm_file://<file_id>`.
- `h3.sh status <task_id>`; `gen --async` submits and returns the task_id without waiting (for wave-of-4 batching).
- Raw endpoints: `POST /v2/video_generation` (multimodal `content[]` array — H3 rejects the v1 endpoint), `GET /v2/query/video_generation/<task_id>` (success → `task.content.url` is the download link directly), `POST /v1/files/upload` with `purpose=video_generation_input`.
- Duration 4–15s int, resolution 768P only. Ratio: required for text-to-video; with image inputs the API DEFAULTS to adapting to the ref's aspect — always send the delivery ratio explicitly (a landscape sheet + `ratio: 9:16` returns 1440×2560, verified). Omit only with first/last-frame keyframes. 4s works fine on the direct API (unlike Higgsfield's 4s failures).
- Task list endpoint covers the last 7 days (`task_type=generation`) — that's the Phase 8 prompt-recovery path for direct-API films.

## Model reference — Higgsfield CLI

Install: `npm i -g @higgsfield/cli`, auth: `higgsfield auth login`, then select a billing workspace first (`higgsfield workspace list` / `workspace set <id>`) — cost and generate calls fail without one.

### MiniMax H3 (`minimax_h3`) — **DO NOT USE for video**

Superseded by official MiniMax API at 768P; Higgsfield H3 is 2K-only and ~2.5× the cost.

- Resolution: **2K only**. Aspect ratios: auto, 21:9, 16:9, 4:3, 1:1, 3:4, 9:16.
- Duration: integer seconds, **5–15** usable (schema says ≥4 but a 4s batch failed 3/3 server-side while 5s+ succeeded — avoid 4).
- Cost: **4 credits/sec** at 2K (verified at 16:9 and 9:16; 5s = 20, 10s = 40, 15s = 60). Failed jobs are NOT charged.
- Media inputs: `--image` (reference), `--start-image`, `--end-image`, reference arrays. A character sheet passed via `--image` keeps the character consistent.
- Discovery: `higgsfield model get minimax_h3 --json`. The schema omits min/max for duration — probe limits with `higgsfield generate cost <model> --duration N` (free) instead of burning a generation.
- Generate: `higgsfield generate create minimax_h3 --prompt "..." --image sheet.png --duration 10 --aspect_ratio 16:9 --resolution 2K --wait --wait-timeout 20m`

### Nano Banana 2 (`nano_banana_2`) — character sheets / stills only

- Produces excellent production-style turnaround sheets (front/side/back + portrait + palette swatches) from a single prompt. Occasional transient HTTP 503 — just retry.

## Cinematic prompt craft (research pass, 2026-08-19 — sources in LEARNINGS Entry 27)

Distilled from the best public work: jnMetaCode/ai-shortfilm-prompts, OSideMedia/higgsfield-ai-prompt-skill, the MiniMax H3 usage manual, and the official Runway/Kling/Sora/Luma prompting guides. These rules override the older heuristics wherever they conflict.

### Prompt anatomy (H3-native)

Per-shot prompt = **shot size + composition → subject (locked description) → ONE action beat in sequential verbs (setup → action → landing) → ONE camera move in its own sentence → named physical light source + locked palette block → style suffix → "One continuous take, no cuts." + "No score. Production audio only."**
- H3 cuts between shots by default — "one continuous take, no cuts" is mandatory.
- H3 does NOT support the legacy Hailuo `[bracket]` camera commands — natural-language camera direction only.
- ~150–200 words per prompt is the sweet spot; walls of adjectives dilute.

### Camera discipline

- **ONE dominant camera move per shot, in its own sentence.** Stacked moves (push + pan + rise) render as unreadable instability. If two are needed, sequence them by time ("rises, holds, then pushes in").
- Melancholy/horror genre pairing: locked-off holds, very slow push-ins, reveal-by-pull-back, slow lateral trucks, end shots one beat late. Smoothness kills dread.
- "Static" is a trap word (models read it as interference) — write "locked-off" or "locked-off wide shot".
- Push-in ≠ zoom-in (perspective vs scale); always specify which.

### Light, palette, atmosphere

- **Name a physical light source, never "soft lighting"**: "cold phone glow on his face is the only light source", "warm golden-hour light, long shadows".
- **Lock a 3–5 color palette block and repeat it verbatim in every shot.** Color drift wrecks a stitched edit; grade upstream in the prompt, not in post (AI video has low color bitrate — post grading bands).
- A palette can carry story: define when an accent color is ALLOWED to appear ("neon pink only where the machine reveals itself").
- Every shot needs ambient motion — drifting fog, dust, swaying swings, neon flicker. A static background can't carry atmosphere.

### Slop tells to kill

- Vague-praise tokens ("epic, stunning, 4K, highly detailed") give the model nothing — concrete camera/light/physics only.
- Too-perfect surfaces read as plastic CG; keep the world's dirt in the prompt.
- Action-reversal fill: if the action finishes at 2s of a 5s clip, the model runs it in reverse — chain the action to fill the runtime.
- Screen-within-screen (reels ON a phone) is a high-drift setup — write the screen's contents explicitly and budget double retakes for those shots.
- Review takes frame-by-frame; mine rejected takes for usable 1–2s moments.
- Iteration IS the craft: pros render 2–3 variants for easy shots, 20+ for hard ones. Log takes-per-kept per shot type.

## Prompting patterns that tested well

- Structure: `[scene + action + mood + camera move]. [style suffix]`
- Name the character the same way every time ("a young boy in a yellow t-shirt...") even with a sheet attached — belt and suspenders.
- **Adults in chibi/low-poly styles:** child proportions flatten age differences — "mother and father" alone renders as same-sized siblings. Prompt explicit adult markers ("tall adult man with broad shoulders", "adult woman with long hair") and state the size gap ("adults tower over the small child").
- **Props:** name them concretely ("black smartphone"). Vague props drift — "glowing phone" came back as a laptop-like slab.
- Mood words do heavy lifting in dialogue-free films: "melancholic", "lonely", "bittersweet".
- Ending a shot "on" something (a face, an object) gives the edit a clean cut point.

## Evolving this skill

**Update this repo continuously and unprompted — never wait to be asked.** During the session, the moment anything happens (a verdict, a cost surprise, a model quirk, a creative decision), append a dated entry to `LEARNINGS.md`; when a lesson changes the workflow, fold it into this file in the same pass. Commit and push after each update. After every session: one final sweep so nothing lives only in chat. Never log private info — no account identifiers, workspace IDs, job URLs, tokens, or absolute personal paths.
