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

## Sources

Both source videos are linked from `SKILL.md`. Summary of where each idea comes from:

- **Six principles** — [youtube.com/watch?v=2TlIg3VokY8](https://www.youtube.com/watch?v=2TlIg3VokY8)
- **Three A/B-test redesigns** — [youtube.com/watch?v=zr37ibqXl1U](https://www.youtube.com/watch?v=zr37ibqXl1U)

All timestamps, percentages (70–90%, 2× loss aversion), and dollar figures ($50 vs $1900, $13–17, $19/mo) are from these videos.

## Ethical use

These techniques exist to **reduce confusion and build trust**, not to manipulate. The skill explicitly calls out dark patterns as off-limits: fake countdown timers, fabricated social proof, hidden losses, hard-to-cancel flows. The guiding test: *if the user understood exactly how this works, would they feel cheated?* If yes, don't ship it.

## License

MIT — see [LICENSE](LICENSE).
