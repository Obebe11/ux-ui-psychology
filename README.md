# UX/UI Psychology — Hermes Agent Skill

A [Hermes Agent](https://hermes-agent.nousresearch.com/) skill that applies behavioral psychology to interface design. It bundles two complementary toolsets:

1. **Six psychological principles** — smart defaults, goal gradient, reciprocity, IKEA/endowment, loss aversion, contrast effect.
2. **Three proven A/B-test redesign patterns** — paywall, ride-hailing, booking — with concrete "Variant A vs Variant B" diffs.

The meta-principle tying them together: **every UI element poses an internal question to the user. The simpler the question, the higher the conversion.**

## What it's for

Load this skill whenever you're:

- Designing or reviewing **onboarding, signup, forms, pricing pages, paywalls, upsells**.
- Investigating **why users drop off** a specific screen.
- Explaining to a client or teammate why "just add a button" won't fix conversion.
- Writing prompts for UI generation tools (`claude-design`, `sketch`, `popular-web-designs`).

It focuses on **behavioral psychology**, not visual aesthetics (colors, typography, grids). Pair it with a visual-design skill when you need the look-and-feel half.

## Structure

| Section | Purpose |
|---------|---------|
| Six Principles — Quick Reference | One-line heuristic per principle, for fast recall. |
| Details & Triggers | When to apply each, why it works, AI-product specifics. |
| A/B-Test Patterns | Three concrete redesigns with element-by-element A/B diffs. |
| Screen Recipes | Ready recipes for onboarding / form / paywall. |
| Ethical Boundary | What's manipulation vs. what's reducing confusion. |
| Common Pitfalls | Mistakes that destroy the effect (e.g. starting progress at 0%). |
| Verification Checklist | Ship-ready checklist for each screen. |

## Install

This is a standard Hermes Agent skill. Drop the `SKILL.md` into your skills directory:

```bash
# User-local (personal, not shared)
mkdir -p ~/.hermes/skills/creative/ux-ui-psychology
cp SKILL.md ~/.hermes/skills/creative/ux-ui-psychology/SKILL.md
```

Or, if you're contributing to a Hermes Agent checkout:

```bash
cp SKILL.md /path/to/hermes-agent/skills/creative/ux-ui-psychology/SKILL.md
```

Reload your session (or start a new one) and the skill will be picked up.

## Use with other AI coding tools

The skill is universal markdown — it works with Claude Code, Codex CLI, OpenCode, Cursor, Gemini CLI, Cline, Continue.dev, Aider, and Windsurf. Each tool has its own convention for where context files live.

**Quick install guide:** see [`guides/`](guides/README.md) for per-tool instructions.

| Tool | Convention | Guide |
|------|------------|-------|
| Hermes Agent | `~/.hermes/skills/<cat>/<name>/SKILL.md` | (this README) |
| Claude Code | `.claude/skills/<name>.md` | [guides/claude-code.md](guides/claude-code.md) |
| Codex CLI | `AGENTS.md` at root | [guides/codex.md](guides/codex.md) |
| OpenCode | `AGENTS.md` at root | [guides/opencode.md](guides/opencode.md) |
| Cursor | `.cursor/rules/<name>.mdc` | [guides/cursor.md](guides/cursor.md) |
| Gemini CLI | `GEMINI.md` at root | [guides/gemini-cli.md](guides/gemini-cli.md) |
| Cline | `.clinerules/` dir | [guides/cline.md](guides/cline.md) |
| Continue.dev | `.continue/rules/<name>.md` | [guides/continue.md](guides/continue.md) |
| Aider | `CONVENTIONS.md` or `--read` | [guides/aider.md](guides/aider.md) |
| Windsurf | `.windsurfrules` at root | [guides/windsurf.md](guides/windsurf.md) |

## Sources

Both source videos are linked from `SKILL.md`. Summary of where each idea comes from:

- **Six principles** — [youtube.com/watch?v=2TlIg3VokY8](https://www.youtube.com/watch?v=2TlIg3VokY8)
- **Three A/B-test redesigns** — [youtube.com/watch?v=zr37ibqXl1U](https://www.youtube.com/watch?v=zr37ibqXl1U)

All timestamps, percentages (70–90%, 2× loss aversion), and dollar figures ($50 vs $1900, $13–17, $19/mo) are from these videos.

## Ethical use

These techniques exist to **reduce confusion and build trust**, not to manipulate. The skill explicitly calls out dark patterns as off-limits: fake countdown timers, fabricated social proof, hidden losses, hard-to-cancel flows. The guiding test: *if the user understood exactly how this works, would they feel cheated?* If yes, don't ship it.

## License

MIT — see [LICENSE](LICENSE).
