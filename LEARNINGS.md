# Learnings Log

Every entry: date, model, cost, verdict (GOOD/BAD/MIXED), and the lesson. Newest first.

---

## 2026-09-13 — Pixel dialogue rejected; alternative style exploration
Director judged the ten-second Bran/Night King pixel conversation unsatisfactory and requested alternative animation-style images. Produced three built-in ImageGen portrait stills of the same two-character meeting for comparison: early-2000s PS2 low-poly 3D, hand-drawn fantasy cel animation, gothic stop-motion puppets. These are still-image proposals only: no alternative-style video generated, no new style approved, and no claim of proven motion fidelity. Keep the current dialogue and scene available while the director selects the next visual direction. Do not assume pixel style remains locked after this feedback.


## 2026-09-13 — Director rejects restart; ten-second dialogue coverage
**BAD:** director rejected the fifteen-second opener for loss of pixel style and incorrect Jon appearance. Text-only casting of a newly introduced character did not preserve identity. Do not reuse this take as a character anchor.
**New direction:** ten seconds at a time, shot by shot. First create a built-in ImageGen portrait with Bran and Night King together, both readable in the same frame, matching the approved pixel stills. This meeting is dialogue coverage; no Jon, combat or origin montage. Show the new still and proposed exact dialogue before its video generation. A ten-second duration is the current project direction, not a universal rule for other films. Do not claim reduced shot complexity guarantees texture preservation; evaluate the next result.


## 2026-09-13 — Restart opener, fifteen seconds
Director authorized one new scene-one sequence: approach, Jon breaking through, Bran saying "You came", sword interception. Submitted full prompt is in prompts/got-restart-scene-01-15s.md. H3 Max I2V, 768P, balanced expansion; approved pixel wide opening still. Delivered fifteen-second MP4. Cost unverified; director verdict pending. Late-frame inspection shows crossed blades but smoother character rendering than the pixel environment, plus Jon appearance drift. Do not mark pixel preservation or new Jon identity as approved. Prior fifteen-second Bran vision draft is superseded by the restart and was never generated.


## 2026-09-13 — GoT pixel film: prompt and feedback failures
Model: fal MiniMax H3 Max I2V/R2V, 768P. Exact billed cost not verified; do not infer spend from historical pricing.

- **BAD — opening style:** illustrated storyboard-guided take lacked the director's requested pixelation. Dedicated built-in ImageGen pixel still then I2V improved fidelity. Director's second opening verdict: "I guess not bad." Character smoothing and added soft light remained; this is tentative acceptance, not perfect fidelity.
- **BAD — Bran ten-second take:** prompt explicitly requested breathing, stillness and leaves, "no dialogue" and "No chest wound insert." It removed the story's reveal and warning. Director rejected the inactivity and absence of speech. Increasing duration without adding narrative was the failure, not evidence that the model cannot tell the story.
- **Correction:** full timed sequence with origin flashback, visible shard/weakness, Bran's warning to Jon and clear speaker-specific audio. The fifteen-second replacement is a DRAFT, not generated or approved yet; see prompts/bran-night-king-15s.md.
- **Prompt standard:** director supplied a detailed adventure-game example with style, cast, geography, timed staging, camera, emotion, sound and exclusions. Adopt its level of specificity, not its unrelated 3D style or 16:9 format. Our film remains pixelated 9:16.
- **Settings truthfulness:** previous jobs used balanced expansion. Director's example reports disabled; verify current support before promising or using it. Store actual submitted and returned expanded prompts separately.
- **Remote source of truth:** the repo already required ongoing updates, but feedback was left in chat. Update actionable lessons after verdicts/corrections and before another generation, reconcile conflicting rules, and push. No promise of autonomous background execution.
- **Approvals:** each still, clip and retry needs its own approval. A script outline is insufficient when the director expects to review the complete submission prompt.



## 2026-09-02 — REFERENCE LOCK: @lucamaxiim study (steal vs never)

### Entry 43 — Variety shorts: steal ingredients, never clone; fal H3 Max 768P price correction — no spend

Ashen studied Instagram @lucamaxiim as a reference, then locked: we are **not** cloning him. We make a variety of random cool animated shorts on fal.ai MiniMax H3 Max 768P. His clothing-brand CTA is not ours. Ours is a Skool community, always "link in bio." Full production lock is in `SKILL.md`.

**STEAL** (ingredients, mix differently every time)
- Obscure specific details (Fiat 500 with four dents; a 2003 Passat driven by a guy named Ethan; a handwritten note from a watchmaker named Wei). Joke lives in the dumb detail.
- Fake institutions that sound real ("Azerbaijan Technology" works as country+corp that should not exist). Invent a NEW one per video. Never reuse his proper nouns.
- Meme lines that should not be in the video ("You met me at a very Chinese time in my life" is a Fight Club splice). Write original splices. Do not repeat his line.
- Picture that does not match the essay. Generated 3D / jank / crash-slop. VO is the point.
- 2–4 word center karaoke captions, white bold fragments, not a subtitle dump.
- Bait then punch. His punch is merch. Ours is never merch.
- ~22–40s, fast 1–2s cuts.

**NEVER**
- His bored / flat / tired narrator cadence. Performance should change per short (hype, sincere, pissed, conspiratorial, tender, theatrical). Variety is the lock. If two in a row could be mistaken for lucamaxiim, rewrite.
- His truck-flag essay skeleton (we all know that one guy / named nobody / fake org / merch) as a clone template.
- His characters/merch: Dante, Skebob, Children of Khan, fish tee, childrenofkhan.com.
- The proper noun "Azerbaijan Technology". The type of joke is fair. The name is his.
- Clothing CTAs. There is no clothing brand.

**OURS**
- Last beat always points at the Skool community via Instagram bio. Rotate: "Learn how we make these videos" / "Learn how to use AI" / "Learn how to make not AI slop" / "Learn how to use AI to make actually good stuff" then "Link in bio."

**Price correction (live fal docs, 2026-09-01):** H3 Max is **$0.02/sec at 768P**, $0.0125/sec at 480P. The old $0.04-then-$0.08 launch line in SKILL.md is stale. Still never generate 480P unless asked. House lock unchanged: fal H3 Max only, 768P, never official MiniMax, never base H3, never 2K/4K.

**Lesson:** Study him for ingredients. Mix them differently every time. Variety is the lock. Do not name a new product line.

---

## 2026-08-31 — PRODUCTION: Grok Imagine × Odyssey contest reel

### Entry 42 — Odyssey Imagine failures from 2026-08-31 session — BAD

Full notes: [`GROK-IMAGINE-ODYSSEY.md`](GROK-IMAGINE-ODYSSEY.md). Contest reel on grok.com Imagine only — this is **not** FAL H3; do not mix pipelines.

**Failures (never repeat)**
- 4-panel board as I2V first frame → slideshow, post `8dc38314`
- Anime / pixel R2V → unmatched slop
- Mini-screenplay timestamps → over-specified, weak
- Short prompt with no event → dead rowing clip
- “one wet glass eye” → jargon, ashen hated it
- “dirty armored men” → wrong period
- One-man skiff on ocean → wrong scale; need full galley + ~30 crew
- One still as only R2V ref for a chase → melt, 180° flip, two-eyed giant, post `008c1f66`
- “Straining in rain” mast prompt → Odysseus screams at crew, men walk in water, post `04fa6823`
- Sat on compose after yes → ashen furious; click that turn
- Still generate aborted then stopped → retry immediately
- Shipped an unwatchable mp4 without watching it

**Lesson:** Use `GROK-IMAGINE-ODYSSEY.md` for look lock, period/cast, Imagine feed rules, and prompt craft. Do not repeat the failures above.

### Entry 41 — Imagine still-then-I2V; one generate; vibe lock; no Extend — MIXED

Contest film on grok.com Imagine only (H3/fal = DQ). Director locked a 3-min gist (not a compressed Odyssey) with Huff-like 1950s grain, VO over picture, CapCut + later Suno.

**GOOD**
- Character turnaround (front/left/right/back) before the character appears. Odysseus has two costumes: lost/dirty for the voyage, cleaned-up for home.
- Storyboards are multi-panel pages with camera notes, not one contact-sheet collage.
- Approve the first-frame still, then one I2V. Chat GenerateImage is boards only.
- Pig-hook 6s I2V held identity, locked-off camera, no extra fingers, no music, strong dark grade + scream audio. That grade is the look lock for the whole film.
- Chat often cannot play mp4s; grok.com Imagine post links play.

**BAD / do not repeat**
- Do not fire multiple Imagine generates hunting a download or a better take. Director: wasting credits. One generate. Do not click Regenerate.
- Prompting "he does not become a pig" on the pig-open produced a frozen cinemagraph. Need hands working the face and a slow human-to-pig morph. Same still, new prompt, one 10s take — do not Extend the frozen 6s to 30s.
- grok.com Imagine on the bot computer is a different session from this chat. Sign-in is one-time. Cursor credits do not buy Imagine video.
- Farmed impression counts (huge impressions, ~400 views) are not the craft model. Watch-through is.

**Lesson:** Imagine contest is a second pipeline in this repo. Never mix it with fal H3 Max. Update this file after every keeper/fail without waiting to be asked.


## 2026-08-29 — HOUSE RULE: fal.ai MiniMax H3 Max at 768P only

### Entry 40 — Swap off official MiniMax onto fal H3 Max 768P — no spend
Director swapped the generation path to **fal.ai MiniMax H3 Max** only. There is no 720p on Max (native 480P or 768P); lock **768P**, the resolution Max is tuned around. A 5-second 768p clip renders in under 3 seconds. Endpoints: `minimax/h3-max/text-to-video` and `minimax/h3-max/image-to-video`. **No official MiniMax** (`api.minimax.io`). **No FAL base H3** (`minimax/h3/*`) even though that path still has reference-to-video. Max has no reference-to-video yet — identity stills are image-to-video first frames. Pricing: $0.04/sec at 768P until 2026-09-01, then $0.08/sec. Auth: `FAL_KEY`. Office grammar (singles, whip from frame zero, room split, spoken numbers as words) is unchanged; only the pipe changed.

---
## 2026-08-27/28 — PRODUCTION: Office mockumentary AI-debate shorts (Michael vs Dwight)

### Entry 39 — Office H3 singles grammar locked; Jim two-shot and numeral-dump rejects — ~$0.80/10s clip

Live-action 9:16 Office mockumentary of Dwight arguing local/Chinese/open-weight models vs Michael arguing American cloud (Claude $20). Native H3 speech. Official MiniMax-H3, 768P, 8–10s singles, concat in ffmpeg. ~$0.80 per 10s clip.

**GOOD**
- One face per generation. Singles cut like the show; two-shots did not.
- FRAME ZERO already a whip pan onto the face, then a short zoom, then settle. A still establishing frame was a reject.
- Separate rooms: Michael in the manager office, Dwight at his own cubicle. Both at the sage-green reception desk read as the same place.
- Slow passion, not scream/chipmunk. Pause between sentences. Fill the 10s.
- Explicit voice lock. Without it, Dwight didn't sound like Dwight and Michael drifted toward Andy Bernard.
- Conversational nerdy lines with one name-drop in the moment (DeepSWE 63.4 / Terminal-Bench 84.3 / supposedly smarter than Claude Opus 5 on MMLU), not an essay and not a numeral dump.
- Michael says the locked Jim lines word for word after the recast. Do not "make it more Michael."
- Fuller Michael line in HIS office ("Okay. Hold on. What are you even asking...") instead of a moan then "that's weird."
- Director stills as `role=reference_image` plus wardrobe/hair/glasses in the prompt. CAST LOCK: exactly one person, adult scale.
- Send each mp4 the moment the job succeeds. Director should never have to ask.
- v5 talking-head confessional remains the gold for interview coverage (separate grammar from argument singles).
- Ghost of Tsushima title plate: locked tripod, ambient-only motion, menu text from frame 0, no left scrim. PS5 grade of 768p rejected; keep original plate.

**BAD / do not repeat**
- v1–v3: slop. v4 fight okay, confessional worse than v5.
- Jim vs Dwight two-shot: Jim looks nothing like Jim (episode screenshots did not lock identity), both far too angry. 1027 `output new_sensitive` on celebrity close-ups. Do not reshoot Jim until better stills.
- v8 two-shot first 10s: shit. Two people in one H3 clip cloned / genericized.
- Starting locked-off then moving later.
- Putting both characters at the reception desk.
- Rushing Dwight; repeating the GLM/DeepSWE/Terminal-Bench open in a later clip.
- Open-weight numeral dump ("262k context. JobBench 55.7. That's 19 points over Opus.") — H3 said "262" not "two hundred sixty two thousand." Felt like random stats. Replacement locked line: local / Uncle Sam / Virginia / Qwen 3.8 Flash Next on a five hundred twelve gigabyte Mac Studio on the desk. Write numbers as full spoken words.
- Michael moaning / swallowing the line. Reinforce SLOW. Clear. Every word.
- Essay-like / press-release dialogue. Must sound like overlapping real conversation.
- MiniMax image-01 hypebeast stills from a tight MCU headshot → bobblehead. Director killed stills; stick to H3 video.
- Waiting to be pinged after a render.
- Punching up locked spoken lines or submitting refs unseen.
- 2K / Higgsfield video / third-party H3 proxies.

**Director ranking:** v5 confessional perfect. v8 singles much better; Michael Kimi/70k and Dwight "loser with an API key" were the bar. Voice retakes of the GLM open + propaganda lines were fine once voice was specified.

**Reproduce:** official `POST /v2/video_generation` at 768P/9:16/10s, one `role=reference_image`, spoken line in `<d>[English] ...</d>`, whip-pan camera block, location split, voice lock, numbers as words, concat keepers.

---
## 2026-08-27 — HOUSE RULE: official MiniMax API + 768P only

### Entry 38 — Director locked official MiniMax API at 768P; 2K and Higgsfield video forbidden — no spend
Director locked all video generation to **MiniMax-H3** via the official MiniMax API (`https://api.minimax.io`) at **768P only**. Higgsfield is not used for video. 2K, H3-Regenerate-2K, and any photoreal 2K override are forbidden. Prompt enhancement and optional Context-IR are OK if vibe/intent stay the same. Direct API is $0.08/sec at 768P vs $0.13/sec at 2K vs ~$0.19–0.20/sec on Higgsfield. Character sheets still via Nano Banana 2; pass sheets as `--ref` on `h3.sh`. Key lives in env `MINIMAX_API_KEY` — never commit it.

---

## 2026-08-20 — PRODUCTION: Episode 4 "Corn" (65.75s, PS1 dither)

### Entry 37 — Ep4 full production, first ZERO-retake run — $6.48 cash + ~4cr sheets
13-shot censorship-safe wake-up call about "corn" addiction (true-crime cold open → kid hooked by the algorithm → brain rewires → relationships/perception ruined → boardroom pivot → way-out montage → phone-doorway closer). Ran autonomously under a goal-mode delegation — the director pre-authorized judging takes solo. **13/13 first-take keepers, zero retakes, zero wasted dollars.**
- **Style A/B ($0.64):** PS1 dither vs N64 fog, same couch scene, 4s/768P. PS1 won on register — grainy, oppressive, true-crime; N64 came back soft/cute (wrong tone for menace). PS1 faces held stable across the whole clip. Locked suffix: `late 1990s PS1 era video game graphics, low poly 3D, heavy screen dithering, wobbling affine textures, jagged aliased edges, chunky visible pixels, dark muted color grading, CRT grain`.
- **Aging two-sheet casting WORKED:** kid sheet + young-man sheet (Nano Banana 2, ~4cr), same outfit palette (grey-beige sweater / dark jeans / white sneakers), round glasses on both. Shots 3→5 match-cut kid→man and the audience reads one character. New casting pattern for age arcs.
- **Recurring surreal signature:** corn stalks growing from the phone (shots 4, 5, 11, 12, 13). First use of a deliberate per-episode motif; rendered reliably when placed concretely in the prompt ("a single small corn stalk sprouts from the bottom edge of the phone").
- **Lesson (judge on LATE frames too):** shot 7's two brain scans only showed one burn pattern at 2.5s — the "patterns light up" action completed by 4.5s and both matched. A mid-clip frame nearly cost an unneeded retake. Check early AND late frames before rejecting a take with a time-locked action.
- **Lesson (abstract shots):** "brain as living circuitry" renders abstract-cavern; acceptable under VO, but pure-interior-concept shots are the most variable. They work when the VO names what we're seeing.
- **Spend:** $6.48 MiniMax cash total (tests $0.64 + wave1 $1.92 + wave2 $1.60 + wave3 $2.32) + ~4cr sheets. Cheapest episode to date (Ep2: 240cr ≈ $12, Ep3: $12.49). Assembly: ffmpeg concat `-c copy -an`, 65.75s, 768×1344 verified. Real copies in film-cut (CapCut rule).
- **State:** film-cut + rough cut + sheets copied to Studio and opened. Notion breakdown shipped. Balance after run: ~$5 MiniMax cash — TOP UP before Ep5.

---

### Entry 36 — Final skill fold-in after "Boiling Point" — no spend
Ep3 closed (footage locked, rough cut, Notion breakdown shipped). End-of-session sweep folded the remaining chat-only lessons into SKILL.md:
- Golden rules renumbered 1–11 (were duplicated/broken); added **#2 never pre-judge takes** (director judges together on the actual files); corrected **#5 casting** — likeness is DESCRIBED, never named (IP checks); **#10 surreal** gained "first and big in the prompt or H3 sheds it" + the director's "more subtle" caveat.
- Style section: H3 carries painterly environments but not anime faces (humans stay retro-game); PS3/GTA-IV suffix added verbatim as the second tested anchor.
- Phase 4: script-presentation rule (scenes as one-liners, VO suggestions below — he records his own VO).
- Phase 5: ffprobe-first-download per batch; seed-to-seed style variance; 4s = montage unit.
- Phase 6: CapCut rejects symlinks — real copies only. Phase order fixed (Assemble before Packaging).
- **House rule in ~/AGENTS.md updated to match Entry 34:** 768P is the standard, 2K photoreal-only (the old line still said "2K only, never 768P").
- **Ops reminder for Ep4:** MiniMax cash balance ~$12 — tell the director to top up before the next production.

---

## 2026-08-19 — PIPELINE MIGRATION: H3 video moved to MiniMax direct API

### Entry 35 — Ep3 "Boiling Point" full footage locked + restructure — $12.49 session spend
Episode expanded mid-flight from a 12-shot Hank-and-lawns film into a 17-shot, 6-act arc after the director's notes: too much lawn/golf, too many "guy standing around" shots, and four required new beats (hypocrisy montage, datacenter-buildout fair point, boycott-futility, Global-South uplift). Final cut order: 01 02 03 / 13 14 15 16 04 07 / 17 / 18 19 20 / 21 22 / 23 12c (~85s).
- **Casting worked:** 3 new sheets (Keanu-coded widower, young-Zuck-coded dorm kid, Jamal-coded Karachi kid) via descriptive prompts (no celebrity names — the Hank-era IP-check lesson holds), Nano Banana 2, 16:9, GTA-IV style. All three read instantly.
- **Lesson (surreal elements):** small/particle surrealism gets SHED by H3 — "blue data-motes rising off lawns" was one clause in a long prompt and never rendered (12b). The whale-led rewrite (12c, surreal element FIRST and huge) rendered. Rule folded into golden rule #7: one mythic element, big and early in the prompt. Director caveat logged: keep the surreal SUBTLE — 12c was "not bad but more subtle next time."
- **Lesson (style variance):** identical suffix, new seed = softer geometry ("looks PS2 not PS3"). Style rolls vary; budget retakes on hero shots.
- **Lesson (delivery):** CapCut import rejects SYMLINKS ("not accessible") — film-cut folders must be real copies. Bytes are cheap; copy, don't link.
- **Lesson (montage pacing):** 4s shots are the right unit for inventory montages; 6 montage items ≈ 24-28s of VO room.
- **State:** 17-shot film-cut folder assembled (`boiling-point/film-cut/`), off to CapCut for the director's VO edit. Session spend $12.49 cash (incl. $1.95 ratio-bug waste + $1.05 closer variants) + ~12cr sheets. Balance ~$12 MiniMax cash remaining — top up before Ep4.

### Entry 34 — HOUSE RULE FLIP: 768P is the new standard — saves 38.5%/sec
Director A/B'd a 768P probe vs the 2K take of Ep3 shot 2 (same prompt, same sheet): "768 looks exactly the same." Verified with native-res frame crops — 2K holds ~10-15% more micro-detail (skin shading, hair strands), all of it invisible at delivery size (feeds serve ~1080px wide) and absorbed by the low-poly/bloom/desaturated PS3 aesthetic.
- **New rule:** video gen defaults to **768P ($0.08/s)**; 2K ($0.13/s) reserved for photoreal styles via explicit `--resolution 2K`. `h3.sh` default flipped (2K now prints the off-rule warning). 5s shot: $0.40 vs $0.65; 12-shot episode: $4.80 vs $7.80.
- **Lesson:** resolution value is style-dependent. Chunky low-poly + bloom + desaturation + motion blur is an aesthetic that IS softness — paying for 2K detail the style throws away is waste. Photoreal is where 768P would fall apart.
- **Watch item:** 768P vertical renders 768×1344 (7:4), ~2% wider than true 9:16 — crop/pad ~15px/side at assembly. Also: the "iterate cheap then final at 2K" pattern stays dead — it only beats direct finals above a ~60% rejection rate, and the final is now 768P anyway.

### Entry 33 — Shot 2 take 1 REJECTED (incrementing counter = slop) + new text rule — $0.65 retake
The 9:16 re-roll of shots 1–3 came back clean and on-model ($1.95, ratio fix held). Shots 1 and 3 kept. Shot 2 rejected: the brief called for a like counter "spinning upward past forty thousand" and floating notification hearts — the incrementing numbers rendered as morphing AI slop.
- **Rule (folded into SKILL.md golden rules):** as little on-screen text as possible, and what exists must be STATIC. One short headline, large font, fixed for the whole take — it may slowly pulse/emanate, never increment. No counters, tickers, badges, or body text. De-emphasize screens (over-shoulder, low in frame); focus on the person, not a macro of the display.
- **Lesson:** rapidly changing numbers/text are the strongest slop tell H3 has — worse than anime faces. Any "engagement goes up" story beat must be carried by performance and framing (face, glow, posture), never by UI motion.
- **Retake prompt change:** macro-of-screen → over-shoulder with the phone low in frame; counter + hearts → one static pulsing headline; focus moved to the girl's glow-lit face.

### Entry 32 — h3.sh ratio bug: ref-attached jobs went 16:9 — $4.42 total ($1.95 wasted + $0.52 verify + $1.95 re-roll)
Ep3 shots 1–3 came back 2560×1440 despite `--ratio 9:16`. Root cause: the wrapper omitted `ratio` whenever a reference image was attached (per the docs note "ratio adaptive with image inputs"), and the char sheets are landscape 1376×768 — so the API adapted to the refs and produced 16:9. Director caught it on review: "this shit is fucking landscape."
- **Fix:** `h3.sh` now ALWAYS sends `ratio` unless a first/last frame is attached (keyframe-locked shots genuinely need adaptive). One 4s verification gen with the landscape girl sheet attached returned **1440×2560** — an explicit `ratio` beats ref-image aspect on the H3 API. Fix verified live before re-rolling.
- **Lesson:** "adaptive with image inputs" is the API's DEFAULT, not a constraint — always pass the delivery ratio explicitly, even with refs attached. Landscape character sheets are fine for 9:16 output as long as `ratio` is sent.
- **Lesson (process):** ffprobe the FIRST downloaded file of every batch against the intended delivery frame (1440×2560) before firing the rest — a $0.52 probe would have caught this before $1.95 of landscape takes.
- **Lesson (docs drift):** the SKILL.md API notes said "ratio omitted/adaptive with image inputs" — that guidance caused the bug. Corrected to: ratio required for t2v, RECOMMENDED explicit with image inputs, omitted only with first/last-frame.

### Entry 31 — Style exploration round 2 + two director rules — $4.50 test spend
Style tests for Ep3 ("Boiling Point", AI-water episode), all 4-5s @ 2K via direct API.
- **Verdicts (director):** anime styles with humans read as AI slop — 90s OVA and watercolor kid shots both rejected. But the OVA/watercolor ATMOSPHERE shots (night car wash, golf course) were "fire" — H3 carries painterly environments, not anime faces.
- **Retro-game family: all four approved.** PS1 (dither/jitter), N64 (blur/fog), PS3/GTA-IV (brown-gray, harsh bloom, plasticky sheen), prerendered-survival-horror. Prerender slightly meh (blocky head). **Ep3 style = PS3.**
- **Rule (casting):** EVERY human in any generation is modeled after a recognizable famous figure — movie/TV/anime/game/historical — anything that stops the scroll. One anchor per episode (Ep3: Hank Hill; future: Batman). Folded into SKILL.md golden rules.
- **Rule (format):** when presenting a script, show the SCENES with the actual generation prompts; the director records his own VO — suggested lines go BELOW the scenes, clearly marked as suggestions.
- **Lesson (H3 vs anime faces):** human faces in anime styles are the slop tell; humans work great in low-poly 3D styles (the series' PS2 kid never read as slop). Keep humans in the retro-game family; painterly styles are for environment-only shots.

### Entry 30 — Direct-API migration: verified end-to-end, ~35% cheaper — $0.96 test spend
Higgsfield bills H3 at 4cr/sec (~$0.19–0.20/sec effective). MiniMax's own pay-as-you-go API bills **$0.13/sec at 2K / $0.08/sec at 768P**, so a 12×5s episode is ~$7.80 vs ~$11.40. Migrated video generation to the direct API; Higgsfield CLI stays for image models (Nano Banana 2 sheets) and ad-hoc hosting.
- **Verified on live tasks:** text-to-video (4s/768P/9:16, ~100s wall clock), reference-image generation with the PS2 char sheet (kid stayed on-model: yellow tee, blue shorts, proportions), and the `h3.sh` wrapper (submit → poll → download) round-trip. 3 test tasks, $0.96 total.
- **Lesson (billing rails):** MiniMax has THREE wallets and only one pays for H3 — pay-as-you-go cash balance via the standard API key. Token Plan subscriptions and prepaid Credits explicitly exclude H3 video ("special models"). Error `1008` = wrong/empty rail, not a bad key.
- **Lesson (endpoints):** H3 requires `POST /v2/video_generation` with a multimodal `content[]` array (v1 endpoint rejects with `2013`). Success returns the download URL directly at `task.content.url` — no file_id exchange. Poll `GET /v2/query/video_generation/<task_id>` every 10s.
- **Lesson (reference images):** upload via `POST /v1/files/upload` with `purpose=video_generation_input`, then pass `mm_file://<file_id>` as an `image_url` item with `role=reference_image`. Uploads live 7 days; image sides must be 256–5760px; first 5 reference images per gen are free. `role=first_frame`/`last_frame` for keyframe-locked shots; `ratio` is required for pure t2v but omitted with image inputs.
- **Lesson (4s works here):** the Higgsfield 4s failures were their proxy, not the model — 4s direct-API tasks succeeded 3/3. Shots can now be sized to 4s for fast VO lines, saving 20%/shot.
- **Lesson (ops):** macOS bash 3.2 + `set -u` chokes on empty arrays (`"${arr[@]}"` unbound) — guard with `${arr[@]+"${arr[@]}"}` in wrappers. Also: `login fail` (1004) on every official host meant a malformed key paste; the real format is `sk-api-…`.
- **State:** wrapper at `~/shorts-factory/h3.sh`, key at `~/.config/shorts-factory/.env`. MiniMax balance $30 (~$29 left). Higgsfield balance 736.2cr held in reserve for image models.

---

## 2026-08-19 — PRODUCTION SUCCESS: "Log Out" complete rough cut

**The full pipeline in this skill produced a finished 62s animated short in one session.** 12 shots, 9:16 2K, PS2 low-poly style, one consistent character throughout, assembled frame-exact at 62.000s. Director's verdict on the final cut: "Okay amazing, this is all really good."

### Entry 29 — Slot Machine wrap: artifact-tolerance precedent + Ep2 breakdown shipped — no spend
Post-production close-out of Episode 2 (same day as Entry 28).
- **Lesson (artifact tolerance):** shot 11 carried a minor head-duplicate artifact (~2s of a 5s clip) on an otherwise perfect take 1. Per the max-3-takes rule it was kept and flagged in the report; the director watched the actual file and approved it as-is. Precedent: a short, non-narrative-breaking artifact on a strong take is acceptable — offer one priced retake (20cr) and let the director decide after watching, don't burn retakes preemptively.
- **Lesson (Phase 8 repeats cleanly):** the Ep2 public breakdown page was built with the exact Phase 8 recipe from Ep1 — verbatim prompts via `generate get --json`, jobs matched to `shot-NN.mp4` by byte size, all 12 videos + rough cut embedded from public CDN/upload URLs. Zero new friction; the recipe is confirmed reusable per episode. Still true: Notion MCP cannot publish — Share → Publish is the director's manual click.
- **State:** two films now exist in the series ("Log Out" 668cr, "Slot Machine" 240cr). Both rough cuts are 62.000s, audio stripped, awaiting director-recorded VO. Balance after Ep2: 736.2cr.

### Entry 28 — PRODUCTION: Episode 2 "Slot Machine" complete — 240cr net, 12/12 keepers, zero taste rejections
First fully unattended goal-mode production. 13 jobs fired, 12 keepers accepted, 1 server-side failure (shot 2, take 1). Ledger (`account transactions`): 256 spent − 16 refunded = **240cr net** vs 668cr for Ep1. Every keeper was accepted on its first WATCHED take — the cinematic-craft prompt anatomy (Entry 27) held across all 12 shots, including all three screen-within-screen hard shots (2, 6, 9).
- **Lesson (screen-within-screen is SOLVED on H3):** "The phone screen clearly shows [explicit content]" + locked-off or single-drift camera rendered legible spinning reels, three-cherry jackpots, clock-coins dropping into a coin slot, and reel symbols of the kid's own life — all first take. The Entry 26 watch item is closed.
- **Lesson (ledger):** failed jobs are not always zero-touch — shot 2's failure charged −16 then refunded +16 four minutes later. Net zero, but the ledger shows both legs; tally net, not gross, and don't panic at mid-run balance dips.
- **Lesson (ops):** fire prompts from files — `--prompt "$(cat .prompt-NN.txt)"` — never inline with apostrophes; an inline em-dash/apostrophe broke one shell command mid-batch (job survived, the wait loop didn't). Also: `generate list` status can flicker completed→in_progress (eventual consistency) — recheck after ~30s before concluding anything.
- **Lesson (review):** watching every take at ~2fps frame dumps is sufficient to catch age drift, palette leaks, and mushy camera moves — no slower review needed.
- **Benchmark updated:** episode 2 in a locked style with locked character: 240cr and ~25 min wall clock. Style exploration (Ep1's ~260cr) is a one-time cost per series.

### Entry 27 — Cinematic craft research pass (GitHub + official guides) — no spend
Director note: "doesn't have to be deadpan — make it as cinematic and beautiful and unique as possible, steal from the best open-source work." Surveyed the highest-signal public repos and official model guides; folded the rules into SKILL.md "Cinematic prompt craft" and applied them to the Slot Machine script v2.
- **Sources:** github.com/jnMetaCode/ai-shortfilm-prompts (~358★, best single find — 5-stage prompt structure, 50-move camera library, genre SOPs), github.com/OSideMedia/higgsfield-ai-prompt-skill (~362★, Higgsfield-native, failure-mode catalog), MiniMax H3 usage manual (via Pixo translation), official Runway Gen-4 / Kling / Sora 2 / Luma prompting guides, prompt-architects slop-tells writeup, github.com/songguoxs/awesome-video-prompts (~575★).
- **Lesson (H3-critical):** the legacy Hailuo `[bracket]` camera commands are documented for V1 models only — H3 wants natural-language camera direction, and cuts between shots by default, so "one continuous take, no cuts" belongs in every single-shot prompt.
- **Lesson:** every vendor's formula converges on the same anatomy — subject → one action → scene → ONE camera move → physical light source → style. One move per shot is the most-repeated rule in the entire corpus.
- **Lesson:** palette lock (3–5 named colors verbatim per shot) + named light sources + ambient motion are the three cheapest anti-slop levers. Grade in the prompt, never in post.
- **Lesson:** iteration is the craft — pros keep 1 in 3-20 takes. Budget retakes by shot difficulty; screen-within-screen is a hard shot type.
- **Note:** this niche formed in 2026 — even the best repos sit at 300-600★; weight production-tested depth over raw stars.

### Entry 26 — Episode 2 greenlit: "Slot Machine" — script phase, no spend
Director picked Slot Machine from the 15-idea list (over Battery Low, the previous top pick). 12-beat script written: the pull-to-refresh feed as a literal slot machine; escalation arc moves the world from playground → casino floor → the house tuning the win rate → unresolved cut-to-black mid-spin. Reuses the locked PS2 style, the same kid/char sheet, and Ep1 locations (bench, playground, tower) as recurring lore — Est. cost ~240 credits (12 × 5s) + retakes, no style exploration needed.
- **Lesson:** a locked style + recurring character turns episode 2 into a pure production exercise — the expensive part of Ep1 (~260cr) was style-finding, which is now a sunk, reusable asset.
- **Watch item:** screen-within-screen shots (reels ON the phone) are the expected drift point; shots 2, 6, 9 carry retake budget.

### Entry 25 — Public breakdown page shipped (Notion) — no credits, pure process
Built the community-facing "how I made it" page for "Log Out" on Notion via MCP: every shot with its verbatim prompt in a code block + embedded output video, char sheet, score audio, full rough cut, cost numbers. Folded the whole recipe into SKILL.md Phase 8.
- **Lesson:** exact prompts are recoverable after the fact — `higgsfield generate list --json` → `generate get <id> --json` → `params.prompt`. Do NOT rely on chat history or memory for the public record.
- **Lesson:** jobs don't map to `shot-NN.mp4` by name or time — match by byte size (`curl -sI <result_url>` content-length vs local file). All 12 shots + sheet + style test + score matched cleanly this way; two unused regens fell out as unmatched.
- **Lesson:** generation result URLs are public CDN links — embed directly, zero hosting step. The assembled rough cut has no URL; `higgsfield upload create` gives it one.
- **Lesson:** Notion MCP can build the full page (video/audio/image embeds from external URLs work), but cannot make it public — Share → Publish is a manual director click.

### Entry 24 — Distribution teardown: top AI-satire reels account (40 reels, 1 week) — Apify scrape
Scraped a leading AI-satire reels account via Apify `instagram-reel-scraper` to reverse-engineer the packaging. Findings folded into SKILL.md Phase 7. Key data: median 104k views, ~5.3% like rate, 6-7 posts/day, ≥50s reels overperform (135k vs 88k median), frame-1 premise cards, fragment-per-shot captions (median 18 chars), ~34 cuts/min, zero hashtags/CTAs, serialized lore + end-card.
- **Validation:** his single most on-brand reel for us ("nostalgia larp") is literally PS2 low-poly 3D — a kid staring at a tablet in a chunky-polygon living room. The "Log Out" aesthetic is proven on this exact audience.
- **Lesson:** study the distribution layer as rigorously as the production layer. A 40-reel scrape via Apify costs almost nothing and replaces vibes with numbers.
- **Lesson (Apify):** use `instagram-reel-scraper` with `{"username":[...],"resultsLimit":40}`; sync endpoint works with a multi-minute curl timeout.

### Entry 23 — Higgsfield audio models discovered — probe costs only
The CLI has a full audio category: `sonilo_music` (text-to-music, **3.75cr for 60s**, 4.07cr for 65s — dirt cheap), `mirelo_text_to_audio` (SFX/ambience, 2.5cr per 10s), plus three TTS models (irrelevant when the director records his own VO). No Suno API path exists, but sonilo_music is a scriptable in-pipeline alternative at trivial cost.
- **Lesson:** `higgsfield model list` shows the whole catalog (3D, audio, image, video, data) — check it before assuming a capability gap. A/B sonilo vs Suno for ambient beds; use mirelo for ambience layers (playground, room tone, city hum) under VO.

### Entry 22 — PROJECT CLOSED: "Log Out" final cost accounting — 668 credits net
Authoritative ledger tally (CLI `account transactions`): 716 credits spent − 48 refunded (failed 4s batch) = **668 credits net** for the complete 62s film, including all style exploration, dead directions, and retries. ~260 of that was style-finding (anchors, probes, dead ends); ~320 was the 12 final shots + fixes; 8 for character sheets. Balance after: 980.27.
- **Lesson:** the transaction ledger (`higgsfield account transactions`) is the only authoritative cost source — session notes undercounted early style tests. Tally from the ledger at project close, not from memory.
- **Benchmark for future films:** a 60s 12-shot film with full style exploration ≈ 650–700 credits. A second film in an ALREADY-locked style should cost ~240 (12× 5s × 4cr) + sheet + retakes buffer ≈ 300. Style exploration is the expensive part; lock styles once, reuse forever.

### Entry 21 — Soundtrack rule added: one Suno prompt per FILM — no cost
Director requirement: every generation session must ship with a Suno prompt for background audio. Key constraint: ONE fluid track for the whole 60s clip, never per-shot. For "Log Out" the brief was foreboding/sad/gloomy/weird-melancholy — delivered two variants (detuned music box + tape hiss; drone-ambient with buried playground sounds).
- **Lesson:** score the film, not the shots. Per-shot music fights the VO; one continuous ambient bed holds a 60s short together.
- **Lesson:** no Suno generation actor exists on Apify (only a downloader) — Suno stays a manual paste-in step until an API path appears. Recheck periodically.
- **Suno craft:** toggle Instrumental explicitly; generate multiple takes and pick the sparsest — the model over-decorates past 30s; explicitly ban drums/drops/structure in the prompt for ambient beds.

### Entry 20 — End-to-end validation: WHAT WORKED, as a recipe
- Concept → style anchors (5s cheap tests) → ONE anchor locked on nostalgic pull (PS2 low-poly beat Ghibli, 90s cel, aggressive retro, VHS)
- In-style character sheet (Nano Banana 2) → passed as `--image` on every character shot → zero character drift across 12 shots
- Style suffix verbatim on every prompt; child proportions + concrete props + adult markers spelled out
- Script sized to VO: 12 beats × ~5s = 62s target hit exactly, no trimming
- Batch generation in waves of ≤4 (concurrency limit), one retry per freed slot, failures never charged
- Assembly: ffmpeg concat demuxer, `-c copy -an` → lossless, instant, exactly 62.000s
- Total spend for the full film including style exploration and all retries: ~400 credits (~$? — record $ per credit when known)
- **This session is the reference implementation of the skill. When in doubt, replay this recipe.**

---

## 2026-08-18 — Production: "Log Out" (62s VO-driven short, PS2 low-poly style)

Film concept: kids-and-phones commentary, voiceover-driven, no character dialogue. Style anchor: **early-2000s PS2 low-poly 3D** (locked after style trials — see entries 9–11). Character: young boy, yellow t-shirt / blue shorts / white sneakers; the 2D anime turnaround sheet was abandoned with the anime direction — a dedicated in-style 3D sheet is required.

### Entry 19 — Shots 6–12 complete + rough cut assembled — batch total 140 credits — GOOD
All 12 shots of "Log Out" banked (12× 5s @ 9:16 2K). Standouts: boardroom with literally faceless suits + kids-on-screens wall + rising chart (shot 8); infinite feed wall (9); city of blue windows (11); foggy playground silhouette closer (12). Shot 7's one-lit-floor tower and shot 10's golden-hour swing both landed first try after retry.
- **Assembly:** `ffmpeg -f concat -c copy -an` across the 12 clips produced exactly 62.000s — no re-encode needed when all clips come from the same model at the same params. `-an` because the film is VO-driven; generated audio is stripped, never evaluated.
- **Lesson:** when every clip shares model/resolution/codec, the concat demuxer with stream copy is the assembly path — instant, lossless, frame-exact.
- **Lesson:** 12× 5s beats landed at the 62s target with zero trimming — sizing shots to VO lines (5–6s) at the script stage works.

### Entry 18 — Concurrency limit discovered, MiniMax H3 — no cost
Firing 7 parallel jobs: 2 rejected immediately with `rate_limit_reached` — `concurrent_jobs_limit: 4` per job set on the Ultimate plan (private workspace). Rejected jobs are NOT charged.
- **Lesson:** max 4 parallel `minimax_h3` generations. Batch in waves of 4; queue the rest and fire as slots free. Applies per model job-set, not account-wide.
- **Lesson:** slot release lags job completion — a retry fired immediately after a completion notification can still bounce with `rate_limit_reached`. Refill only on the NEXT completion (or add a short delay), never assume a just-finished job freed its slot instantly.

### Entry 17 — Full-batch generation of remaining shots, MiniMax H3, 7× 5s @ 9:16 2K, 140 credits — fired
Director approved shots 1–5 ("these look sick") and ordered the rest in one batch. Production decisions:
- Shots WITHOUT the kid in the foreground (tower, boardroom, feed wall, city pull-back, final silhouette) run style-suffix-only, no `--image` sheet — prevents the reference from bleeding onto extras/backgrounds.
- Keepers staged in a project folder (`log-out/shots/`) with clean names, plus the sheet and style reference, instead of loose Downloads files.
- **Lesson:** batch the remaining shots once the director approves the look — per-shot approval is for the style-finding phase, not the rolling phase.
- **Lesson:** skip the character sheet on shots where the character is absent or a distant silhouette; the reference image is a strong prior and will contaminate scenes that shouldn't feature him.

### Entry 16 — Shot 1 v2 (adult parents fix), MiniMax H3, 5s @ 9:16 2K, 20 credits — GOOD
Applied Entry 14's lessons: "tall adult man with broad shoulders, adult woman with long hair, adults tower over the small child" + "black smartphone". Parents now read unmistakably as adults (angular tall dad, long-haired mom), both heads-down on black phones; push-in ends on the kid's blue-lit face with the glowing phone on the table before him — clean cut point, exactly the handover beat.
- **Lesson confirmed:** explicit adult markers + stated size gap reliably fixes parent/child ambiguity in low-poly chibi styles. One regen, no iteration loop.

### Entry 15 — Shots 4 & 5, PS2 style with sheet, MiniMax H3, 2× 5s @ 9:16 2K, 40 credits — GOOD (pending director)
- Shot 4 (hallway): kid walks toward camera between locker rows; every background kid head-down on a glowing phone, faces blue-lit. On-model, composition exactly as prompted.
- Shot 5 (cafeteria): near-table kid alone on his phone, rows of kids at far tables all on phones. Prompt asked for "one long table, group at far end" — model split into separate cafeteria tables. Beat still reads ("together but alone"), so accepted.
- **Lesson:** group-table blocking ("at the other end of HIS table") is unreliable; the model prefers its own cafeteria layout. If exact spatial blocking matters, say it twice or use a keyframe.
- **Observation:** with the sheet attached, background kids also inherit the yellow-tee look occasionally (shot 4 has a yellow-shirt background kid) — the sheet bleeds onto extras. Harmless at fog distance, but for crowd shots consider "other kids in varied colored shirts" in the prompt.

### Entry 14 — Shots 1 & 3, PS2 style with sheet as `--image`, MiniMax H3, 2× 5s @ 9:16 2K, 40 credits — MIXED
Sheet-as-reference pipeline works: the kid stayed on-model (yellow tee, proportions) in both.
- Shot 3 (bedroom, blue glow on face, moonlit window): STRONG. Reads as a child, mood lands, on-model. Candidate keeper.
- Shot 1 (dinner table): mood/composition right (dim room, family heads-down on glowing screens) but the "mother and father" rendered as child-sized siblings — in low-poly chibi proportions, adults and kids look the same age unless you differentiate. The slide-the-phone beat also read ambiguously (glowing object read as a laptop).
- **Lesson:** low-poly child proportions flatten age differences. For adults, prompt explicit adult markers: "tall adult man with broad shoulders" / "adult woman with long hair," and state the size gap ("adults tower over the small child"). Don't rely on "mother and father" alone.
- **Lesson:** specify key props concretely ("black smartphone") — "glowing phone" drifted into a laptop-like slab.
- **Observation:** sheet-referenced shots render slightly cleaner/smoother than the raw PS2 test (less grime/aliasing). The reference image pulls toward its own cleanliness. Acceptable, but if more grit is wanted, push the texture words harder when a sheet is attached.
- **Director verdict (both): "looks lit"** — shot 1 accepted despite parents reading as siblings (Entry 14's adult-marker lesson logged but NOT applied; director judged the vibe over literal accuracy). Shot 3 accepted as-is.

### Entry 13 — PS2 character sheet, Nano Banana 2, 1 image — GOOD (pending director)
Dedicated in-style 3D turnaround (front/side/back/three-quarter) for the "Log Out" kid: young Pakistani boy, ~10, brown skin, messy black hair, yellow tee / blue shorts / white sneakers, child proportions with oversized head. Prompt spelled out "child proportions with oversized head and short stature" — result reads clearly as a kid. Replaces the abandoned 2D anime sheet as the `--image` reference for all PS2 shots.
- **Lesson:** one sheet per STYLE, not per film. When the style anchor changes medium (2D cel → 3D low-poly), regenerate the sheet in the new medium before rolling shots.

### Entry 12 — Shot 2 (playground bench), PS2 style, MiniMax H3, 5s @ 9:16 2K, 20 credits — pending director verdict
Kid alone on a bench hunched over a glowing handheld, other kids playing in fog behind him, empty swings. Prompted child proportions explicitly ("small child, young kid proportions, oversized head"). On review: the kid finally reads as a CHILD (big head, small body) — the Entry 9 grown-man defect is fixed. Fog, muddy ground, muted grade all landed; background kids animate while he stays locked on the screen, which carries the beat.
- **Lesson:** "young kid proportions, oversized head, short stature" in the prompt reliably fixes age drift in low-poly 3D styles. Include on every shot with the kid.

### Entry 11 — Shot 1 v3 (aggressive retro anime): REJECTED — retro direction dead — 20 credits
v3 used the hard-pushed retro suffix from Entry 8 (1980s hand-painted, thick ink outlines, heavy grain, dust and scratches). The retro look landed this time, but the director rejected it anyway ("shit too"). All 2D anime directions (Ghibli, 90s cel, aggressive retro, blend) are now dead for this film.
- **Lesson:** a style can execute correctly and still be wrong for the project. Style selection is taste, not correctness — test cheap (5s anchors) before committing shots.
- **Decision:** PS2 low-poly is the film's style. Reference clip: the original PS2 test (kid running, foggy sidewalk). Every shot gets the PS2 suffix verbatim (Entry 9).

### Entry 1 — Shot 1 (dinner table), MiniMax H3, 10s @ 16:9 2K, 40 credits — GOOD
Slow push-in, two adults on glowing phones hand the kid a phone; ends on close-up of his face. Character sheet passed as `--image` reference — kid stayed perfectly on-model. Minor deviation: both adults read as older women instead of mom+dad; harmless.
- **Lesson:** `--image <character-sheet>` on every shot works for consistency. Do it always.
- **Lesson:** "slow push-in" executed cleanly, ending on a face = clean edit cut point.

### Entry 2 — Style anchor tests, MiniMax H3, 3× 5s @ 16:9 2K, 60 credits total — MIXED
Same scene (kid running in nature) in three styles: Ghibli-painterly, 90s cel, Ghibli/90s blend.
- Ghibli: prettiest image, minor background shimmer. GOOD.
- 90s cel: strongest identity (flat cel, grain, retro palette) but worst motion artifacts — mid-clip zoom caused face ghosting/doubling. MIXED → usable with calm cameras.
- Blend: cleanest motion but failed to differentiate (read as generic modern anime). BAD → don't prompt two styles at once.
- **Lesson:** test styles on the same simple scene, one variable at a time; pick ONE anchor.
- **Lesson:** avoid zooms/fast camera moves in 90s cel style — that's where faces break.

### Entry 3 — Duration probing, MiniMax H3 — no cost
`higgsfield model get` omits duration min/max. `generate cost` calls are free and validate params server-side.
- Discovered: duration integer, errors below 4 and above 15. 4s generation batch failed 3/3 server-side (no charge); 5s+ all succeeded.
- **Lesson:** probe limits with `generate cost`, never with paid generations. Avoid 4s.

### Entry 4 — Character sheets, Nano Banana 2, 2 images — GOOD
One prompt each produced full turnaround sheets (front/side/back + portrait + palette) in both target styles. One request hit a transient HTTP 503; retry succeeded.
- **Lesson:** 503s on this API are transient — retry before changing anything.
- **Lesson:** lock outfit colors in the sheet prompt; reuse the exact outfit words in every shot prompt.

### Entry 10 — VHS 80s style test: BAD (director: "buns") — 20 credits
Requested 1980s VHS cartoon with scan lines/tape artifacts/tracking distortion. Result: clean, bright, modern-looking cheerful kids' cartoon; analog artifacts didn't materialize; tone far too cheerful for a melancholic film.
- **Lesson:** analog artifact keywords ("scan lines", "tracking distortion", "VHS softness") are unreliable on MiniMax H3 — the model may ignore texture instructions that fight its clean default. Don't build a film's identity on artifacts the model won't reliably produce.
- **Lesson:** mood words in the scene description ("sunny", "cheerful" scenarios) can overpower the style intent. Keep scene mood aligned with the film's tone even in throwaway tests — style AND tone are both being tested.

### Entry 9 — PS2 low-poly style test: GOOD — director's favorite
5s PS2-era low-poly test (foggy draw distance, muted gray-brown grade, flat textures, follow-from-behind camera) — director: "infinitely better, I love that one." Strong nostalgic pull confirmed.
- **Lesson:** PS2/early-3D game aesthetic is a top-tier nostalgia anchor for this audience. Prompt keys that worked: "early 2000s PS2 era video game graphics, GTA style low poly 3D, flat muddy textures, jagged aliased edges, muted gray-brown color grading, foggy draw distance, RenderWare aesthetic."
- **Defect noted by director:** character read as a grown man, not a child. Cause: no character reference attached (anime sheet is the wrong medium) and "boy" is weak in prompts.
- **Lesson:** for 3D/low-poly styles, generate a DEDICATED character sheet in that style, and prompt child proportions explicitly ("young boy, child proportions, oversized head, short stature"). Reusing a 2D anime sheet for 3D styles is untested and likely counterproductive.

### Entry 8 — Shot 1 v2 verdict: REJECTED (too generic) — 20 credits
The 9:16/5s dinner shot (suffix: "1990s retro anime style, cel shaded animation, film grain, vintage anime aesthetic") came back clean, polished, modern-looking. Director rejected it: "everyone does this, it's too bullshit, make it more unique."
- **Lesson:** mild retro suffixes ("1990s retro anime style, film grain") are not strong enough — the model drifts to its polished default, especially in dark interior scenes. Retro must be pushed HARD and concretely: "1980s hand-painted anime, thick hand-inked outlines, muted faded color palette, heavy film grain, dust and scratches, slight VHS softness, hand-painted background art, on-twos animation feel."
- **Lesson:** style intensity ≠ style keywords. Texture-level instructions (ink, dust, frame rate) beat era labels.
- Also fixed in v3 prompt: parents specified as "a mother and father" (model kept improvising two women).

### Entry 7 — Director note: nostalgia is the quality lever
Creative direction from the director: nostalgia automatically raises perceived quality. Any style/framing/texture with nostalgic pull (90s cel, PS2 low-poly, VHS artifacts, film grain) beats a prettier-but-generic look. Ghibli-painterly specifically called out as overdone and NOT nostalgic — deprioritized despite testing prettiest.
- **Lesson:** when choosing between style anchors, weigh nostalgic resonance as a first-class criterion, not just image quality. "Pretty" loses to "feels like childhood."

### Entry 6 — Aspect ratio & pacing pivot — 40 credits wasted — BAD (process miss)
Shot 1 was generated at 16:9/10s per the original plan, then the director revealed the target is vertical (9:16) and that 10s feels way too long under VO. The 16:9 take is unusable for the final cut.
- **Lesson:** confirm the DELIVERY PLATFORM (vertical vs horizontal) in Phase 1, before any generation. Aspect ratio is a day-one decision.
- **Lesson (VO pacing):** one spoken line ≈ 5–6 seconds. A 10s shot forces padding or dead air. For VO-driven shorts, default shot duration ≈ 5–6s per narration line; write the VO lines first, then size shots to them. More, shorter shots also cut cheaper (per-second pricing is linear).
- **Lesson:** a 16:9 character sheet still works fine as an `--image` reference for 9:16 generations — it's a reference, not a frame.

### Entry 5 — Ops notes, Higgsfield CLI
- `higgsfield workspace set <id>` is required before `generate cost`/`generate create` — error message says so, but it's easy to hit first.
- Failed jobs are not charged (verified: balance unchanged after 3 failed jobs).
- **Lesson:** select the workspace at session start; check balance before/after batches.
