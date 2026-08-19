# Learnings Log

Every entry: date, model, cost, verdict (GOOD/BAD/MIXED), and the lesson. Newest first.

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
