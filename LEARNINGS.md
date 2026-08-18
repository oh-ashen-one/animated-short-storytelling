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

### Entry 5 — Ops notes, Higgsfield CLI
- `higgsfield workspace set <id>` is required before `generate cost`/`generate create` — error message says so, but it's easy to hit first.
- Failed jobs are not charged (verified: balance unchanged after 3 failed jobs).
- **Lesson:** select the workspace at session start; check balance before/after batches.
