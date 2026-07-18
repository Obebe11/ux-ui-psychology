# Cursor

[Cursor](https://cursor.com) (the AI code editor) uses **rules** stored in `.cursor/rules/`. There are two rule types:

- **Project Rules** (`.cursor/rules/*.md`) — modern, git-tracked, with structured frontmatter.
- **Global Rules** (`~/.cursor/rules/*.md`) — personal, apply to all projects.

Project Rules support a `description` field that Cursor uses to decide when to surface the rule — similar to Hermes' skill loading.

## Install

### Project Rule (recommended)

```bash
mkdir -p .cursor/rules
cp SKILL.md .cursor/rules/ux-ui-psychology.mdc
```

Then edit the file to add Cursor's frontmatter at the top (Cursor uses `.mdc` extension):

```markdown
---
description: UX/UI psychology — 6 principles + 3 A/B-test patterns. Use when reviewing or designing interfaces: onboarding, forms, pricing pages, paywalls, booking screens.
globs: ["src/components/**", "app/**", "web/**", "**/*.tsx", "**/*.vue"]
alwaysApply: false
---

# UX/UI Psychology

[... rest of SKILL.md body ...]
```

The `globs` field tells Cursor to auto-attach this rule when editing UI files. `alwaysApply: false` means Cursor only loads it on match — keeping context lean.

### Strip the Hermes frontmatter first

The Hermes YAML block at the top of `SKILL.md` will conflict with Cursor's frontmatter. Remove it:

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > /tmp/skill-body.md
```

Then prepend Cursor's frontmatter manually.

### Global Rule

```bash
mkdir -p ~/.cursor/rules
# Same as above, but in ~/.cursor/rules/
```

## Usage examples

In Cursor's chat (Cmd+L / Ctrl+L):

```
Review src/components/Paywall.tsx for UX psychology issues
```

Cursor will auto-attach the rule if you're editing a matching file, or you can explicitly reference it:

```
@ux-ui-psychology Review this pricing page for loss aversion framing
```

## Cursor specifics

- **`.mdc` extension** — Cursor uses `.mdc` (Markdown with config) for rules. `.md` works but `.mdc` enables the editor UI.
- **`globs`** — critical for auto-attachment. List your UI directories.
- **`alwaysApply: true`** — use only if you want the skill in every chat. Usually `false` + good `globs` is better.
- **Cursor ignores `description` length limits** in practice, but keep it under ~200 chars for the picker UI.
- **Settings > Features > RulesForAI** is the legacy location — prefer `.cursor/rules/`.
