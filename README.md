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

The skill is generator-agnostic, but the logged production experience uses:

- **Higgsfield CLI** (`npm i -g @higgsfield/cli`) — access to many video/image models through one CLI
- **MiniMax H3** (`minimax_h3`) — anime-capable video model, 2K, up to 15s per clip
- **Nano Banana 2** (`nano_banana_2`) — character reference sheets

## Contributing / evolving this skill

This file is meant to grow. After any production session:

1. Append what you learned to `LEARNINGS.md` (date, model, cost, verdict, lesson).
2. If a lesson changes the *workflow*, fold it into `SKILL.md` itself.
3. No private information: no account emails, workspace IDs, job URLs, tokens, or personal file paths.

## License

MIT — take it, use it, improve it, share it.
