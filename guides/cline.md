# Cline

[Cline](https://cline.bot) (VS Code extension, formerly "Claude Dev") reads project rules from:

- **`.clinerules`** — a single file (legacy, simpler)
- **`.clinerules/`** — a directory of `.md` files (modern, modular)

The directory form lets you organize multiple rules and Cline will load all of them.

## Install

### Directory form (recommended)

```bash
mkdir -p .clinerules
cp SKILL.md .clinerules/ux-ui-psychology.md
```

Cline will automatically pick up this file as project context.

### Single-file form

```bash
cat SKILL.md >> .clinerules
```

Use this if you don't need multiple rule files. Note: this appends, so you can combine multiple skills into one `.clinerules`.

## Strip the Hermes frontmatter

Cline reads the body as text. The YAML frontmatter works but wastes context tokens. Optional cleanup:

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > .clinerules/ux-ui-psychology.md
```

## Usage examples

In the Cline VS Code extension panel:

```
Review src/components/Paywall.tsx against the UX psychology rules in .clinerules/
```

Cline will read the rules from `.clinerules/` automatically and apply them.

## Cline specifics

- **Always loaded** — Cline reads `.clinerules/` on every session start. There's no per-prompt gating.
- **Directory form scales** — add more skills as separate `.md` files. Cline concatenates them.
- **Git-track `.clinerules/`** for team consistency.
- **`~/.clinerules/`** doesn't exist as a convention — Cline rules are per-project.
- **vs. `.cursorrules`** — Cline is the successor convention. If migrating from Cursor, rename `.cursorrules` → `.clinerules`.
- **MCP support** — Cline supports MCP servers via its settings UI, separate from rules.

## Pair with Cline's "Plan" mode

Cline has a Plan mode (similar to Claude Code's). For UX redesigns:

1. Switch to **Plan Mode** in the Cline panel.
2. Prompt: *"Plan a redesign of the onboarding flow using the 6 UX principles."*
3. Review the plan, then switch to **Act Mode** to implement.

This two-phase flow matches the skill's structure (principles → recipes → implementation).
