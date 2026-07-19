# UX/UI Psychology — Hermes Agent Skill

**English** · [Русский](README.ru.md)

A [Hermes Agent](https://hermes-agent.nousresearch.com/) skill with trigger → action rules for interface design. It bundles three complementary toolsets:

1. **Six psychological principles** — each with a concrete trigger (when to apply) and action (what to change).
2. **Three A/B-test patterns** — paywall, ride-hailing, booking — as actionable rules, not case studies.
3. **Paywall triggers** — concrete screen-level, CTA, trial, and pricing triggers drawn from a study of 2,995 paywalls.

The meta-principle tying them together: **every UI element poses an internal question to the user. The simpler the question, the higher the conversion.**

## What it's for

Load this skill whenever you're:

- Designing or reviewing **onboarding, signup, forms, pricing pages, paywalls, upsells**.
- Investigating **why users drop off** a specific screen.
- Explaining to a client or teammate why "just add a button" won't fix conversion.
- Writing prompts for UI generation tools (`claude-design`, `sketch`, `popular-web-designs`).

It focuses on **behavioral psychology**, not visual aesthetics (colors, typography, grids). Pair it with a visual-design skill when you need the look-and-feel half.

## Structure

This skill uses **progressive disclosure** — a thin entry point (`SKILL.md`, ~6 KB) that loads on every relevant task, with deep material in `references/` loaded only when needed.

```
ux-ui-psychology/
├── SKILL.md                          # Entry point (~5 KB, always loaded)
├── references/
│   ├── principles.md                 # 6 principles as Trigger → Action
│   ├── ab-test-patterns.md           # 3 patterns as Trigger → Action
│   ├── paywall-patterns.md           # Paywall triggers: screen, CTA, trial, pricing
│   ├── screen-recipes.md             # Ready recipes for 8 screen types
│   └── ethics-and-pitfalls.md        # Ethical boundary, 10 pitfalls, ship checklist
├── guides/                           # Per-tool install guides (Claude Code, Codex, Cursor, …)
├── README.md (EN), README.ru.md (RU)
├── LICENSE
└── .gitignore
```

| File | Purpose |
|------|---------|
| `SKILL.md` | Quick reference tables + pointers. Loaded on every task. |
| `references/principles.md` | Each principle as a trigger, action, and pitfall. |
| `references/ab-test-patterns.md` | Three patterns as trigger → action rules. |
| `references/paywall-patterns.md` | Concrete paywall triggers: screen-level, CTA, trial, pricing, framing. |
| `references/screen-recipes.md` | Onboarding, form, paywall, booking, landing, churn, empty state, notifications. |
| `references/ethics-and-pitfalls.md` | What not to do, why, and a ship-ready checklist. |

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

All three source videos are linked from `SKILL.md`. Summary of where each idea comes from:

- **Six principles** — [youtube.com/watch?v=2TlIg3VokY8](https://www.youtube.com/watch?v=2TlIg3VokY8)
- **Three A/B-test redesigns** — [youtube.com/watch?v=zr37ibqXl1U](https://www.youtube.com/watch?v=zr37ibqXl1U)
- **2,995 paywalls study** — [youtube.com/watch?v=9ypqs_2fAl8](https://www.youtube.com/watch?v=9ypqs_2fAl8)

All timestamps, percentages (70–90%, 2× loss aversion), and dollar figures ($50 vs $1900, $13–17, $19/mo, Opal 7→17%, Outsider 5×) are from these videos.

## Ethical use

These techniques exist to **reduce confusion and build trust**, not to manipulate. The skill explicitly calls out dark patterns as off-limits: fake countdown timers, fabricated social proof, hidden losses, hard-to-cancel flows. The guiding test: *if the user understood exactly how this works, would they feel cheated?* If yes, don't ship it.

## License

MIT — see [LICENSE](LICENSE).
