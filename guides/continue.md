# Continue.dev

[Continue.dev](https://continue.dev) is an open-source AI code assistant for VS Code and JetBrains. It supports **rules** (also called "instructions") loaded from `.continue/rules/`.

## Install

```bash
mkdir -p .continue/rules
cp SKILL.md .continue/rules/ux-ui-psychology.md
```

### Add Continue frontmatter

Continue supports optional frontmatter for rule selection. Add at the top:

```markdown
---
description: UX/UI psychology — 6 principles + 3 A/B-test patterns. Apply when reviewing or designing interfaces.
globs: ["src/components/**", "app/**", "**/*.tsx", "**/*.vue", "**/*.html"]
---

# UX/UI Psychology

[... rest of SKILL.md body ...]
```

### Strip the Hermes frontmatter first

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > /tmp/skill-body.md
```

Then prepend Continue's frontmatter.

## Global rules (all projects)

```bash
mkdir -p ~/.continue/rules
cp SKILL.md ~/.continue/rules/ux-ui-psychology.md
```

## Usage examples

In Continue chat (VS Code: Cmd+L):

```
Review the paywall component for UX psychology issues
```

Continue will auto-attach the rule based on `globs` when you're editing matching files.

## Continue specifics

- **Rule selection** — Continue uses the `description` and `globs` fields to decide when to attach the rule. Good globs are critical.
- **Always-on alternative** — if you want the rule on every chat, omit `globs` and set `alwaysOn: true` (Continue 0.9+).
- **`@rules`** — you can explicitly reference a rule in chat with `@ux-ui-psychology`.
- **`.continue/rules/` is per-project. `~/.continue/rules/` is global.**
- **Continue also supports config.yaml** at `~/.continue/config.yaml` for global instructions — don't put skills there, use the rules directory.

## Continue vs. Cursor rules

Continue rules and Cursor rules are structurally similar but not interchangeable:

| Aspect | Cursor | Continue |
|--------|--------|----------|
| Location | `.cursor/rules/*.mdc` | `.continue/rules/*.md` |
| Extension | `.mdc` | `.md` |
| Frontmatter | `description`, `globs`, `alwaysApply` | `description`, `globs`, `alwaysOn` |
| Global | `~/.cursor/rules/` | `~/.continue/rules/` |

If migrating between the two, the body content transfers directly; only the frontmatter needs adjustment.
