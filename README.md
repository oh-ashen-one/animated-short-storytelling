# Animated Short Storytelling

A living skill file for producing **short animated films with AI video models** — from concept to final cut. Built and battle-tested during real productions, updated every time something works or fails.

The goal: any agent (or human) can pick this up in a fresh session and produce a coherent, character-consistent animated short without re-learning expensive lessons.

## What this is

- **`SKILL.md`** — the skill itself. Load it into any skill-compatible agent (Claude Code, Kimi Code, Codex, Cursor, etc.) or just read it. Contains the full production workflow, model reference, cost math, and prompting patterns.
- **`LEARNINGS.md`** — the production log. Every generation session appends dated, scored lessons: what was generated, which model, what it cost, whether the result was good or bad, and why.

## Quick start

1. Install the skill: drop this repo's `SKILL.md` into your agent's skills directory (e.g. `~/.agents/skills/animated-short-storytelling/SKILL.md`), or reference it directly.
2. Read `SKILL.md` → **Workflow** and follow the phases in order: concept → style anchors → character sheet → shot list → generate → assemble.
3. Before burning credits, read **Model reference** and **Lessons learned** — they will save you money.

## Current toolchain

**Video generation is MiniMax H3 only, via MiniMax's official pay-as-you-go API, at 768P.** Never Higgsfield for video. Never 2K. Never H3-Regenerate-2K.

- **MiniMax-H3 (official API)** — `https://api.minimax.io`, docs at [platform.minimax.io](https://platform.minimax.io/docs/api-reference/video-generation-v2-create). Model `MiniMax-H3`, resolution `768P`, 4–15s per clip, native audio. Auth: env `MINIMAX_API_KEY` (pay-as-you-go). Never commit the key.
- Prompt enhancement is allowed (stronger camera/light/performance, optional H3-Context-IR) as long as the user's vibe and intent stay the same.
- **Nano Banana 2** — character reference sheets / stills only, not video.

## Contributing / evolving this skill

This file is meant to grow. After any production session:

1. Append what you learned to `LEARNINGS.md` (date, model, cost, verdict, lesson).
2. If a lesson changes the *workflow*, fold it into `SKILL.md` itself.
3. No private information: no account emails, workspace IDs, job URLs, tokens, or personal file paths.

## License

MIT — take it, use it, improve it, share it.
