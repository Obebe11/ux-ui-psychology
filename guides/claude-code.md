# Claude Code

[Claude Code](https://docs.claude.com/en/docs/claude-code) (Anthropic's CLI) supports two related mechanisms:

- **Skills** (`.claude/skills/*.md`) — markdown guides Claude loads when a task matches.
- **Slash commands** (`.claude/commands/*.md`) — manually invoked via `/name`.
- **CLAUDE.md / Rules** (`.claude/rules/*.md`) — always-loaded context.

For this UX/UI skill, use the **Skills** mechanism — Claude loads it automatically when you ask about interface design, without cluttering every conversation.

## Install

```bash
# Project-level (shared with team, git-tracked)
mkdir -p .claude/skills
cp SKILL.md .claude/skills/ux-ui-psychology.md

# Or user-level (global, personal)
mkdir -p ~/.claude/skills
cp SKILL.md ~/.claude/skills/ux-ui-psychology.md
```

## Strip the Hermes frontmatter (optional)

Claude reads the body as text, so the YAML frontmatter works but wastes context. Optional one-liner to drop it:

```bash
# Keep everything after the closing "---" of the frontmatter
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > .claude/skills/ux-ui-psychology.md
```

## Verify it's loaded

In an interactive `claude` session:

```
/help
```

Your skill should appear in the list. Alternatively, just ask:

> *What UX/UI psychology principles do you know?*

Claude should reference the 6 principles + A/B-test patterns.

## Usage examples

Once installed, Claude will surface this skill on matching prompts:

```
# Review a paywall
claude -p "Review src/components/Paywall.tsx against UX psychology best practices" \
  --allowedTools Read --max-turns 5

# Design an onboarding flow
claude -p "Design a 3-step onboarding for our AI resume builder using behavioral principles" \
  --max-turns 8

# Audit a landing page
cat landing.html | claude -p "Run this landing through the 6 UX principles + A/B-test patterns"
```

## Pair with custom subagents (optional)

For repeated UX review work, define a subagent that always loads this skill:

```markdown
# .claude/agents/ux-reviewer.md
---
name: ux-reviewer
description: UX/UI psychology review
model: sonnet
tools: [Read, Bash]
---
You are a UX reviewer. Always apply the principles from .claude/skills/ux-ui-psychology.md:
the 6 psychological principles, 3 A/B-test patterns, and the ethical boundary.
Report findings as a table: principle → current state → recommended change → expected impact.
```

Invoke with: `@ux-reviewer review the new pricing page`
