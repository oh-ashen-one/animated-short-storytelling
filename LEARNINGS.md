# Learnings Log

Every entry: date, model, cost, verdict (GOOD/BAD/MIXED), and the lesson. Newest first.

---

## 2026-08-18 — Production: "Log Out" (62s VO-driven short, 90s cel anime style)

Film concept: kids-and-phones commentary, voiceover-driven, no character dialogue. Style anchor: 1990s retro cel anime. Character: young boy, yellow t-shirt / blue shorts / white sneakers, locked via Nano Banana 2 turnaround sheet.

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
