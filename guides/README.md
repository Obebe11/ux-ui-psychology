# Guides: Use this Skill with AI Coding Tools

The skill's content — 6 UX/UI psychology principles + 3 A/B-test patterns — is **universal markdown**. What changes per tool is *where the file goes* and *how it's invoked*. This directory has a short install guide for each popular AI coding CLI/IDE.

## Quick Reference

| Tool | Convention | Install guide |
|------|------------|---------------|
| **Hermes Agent** | `~/.hermes/skills/<category>/<name>/SKILL.md` | [README](../README.md) |
| **Claude Code** | `.claude/skills/<name>.md` | [claude-code.md](claude-code.md) |
| **Codex CLI** | `AGENTS.md` at project root | [codex.md](codex.md) |
| **OpenCode** | `AGENTS.md` at project root | [opencode.md](opencode.md) |
| **Cursor** | `.cursor/rules/<name>.md` | [cursor.md](cursor.md) |
| **Gemini CLI** | `GEMINI.md` at project root | [gemini-cli.md](gemini-cli.md) |
| **Cline** | `.clinerules` file or `.clinerules/` dir | [cline.md](cline.md) |
| **Continue.dev** | `.continue/rules/<name>.md` | [continue.md](continue.md) |
| **Aider** | `CONVENTIONS.md` at project root | [aider.md](aider.md) |
| **Windsurf** | `.windsurfrules` at project root | [windsurf.md](windsurf.md) |

## General principle

The Hermes YAML frontmatter at the top of `SKILL.md` is harmless in other tools — they just read it as text. You can:

- **Keep it as-is** — works everywhere, costs ~10 lines of context.
- **Strip it** — `tail -n +12 SKILL.md > skill-body.md` removes everything before the body.
- **Adapt it** — Cursor and Continue have their own frontmatter schema (see their guides).

## Trigger phrases that work across all tools

Once the skill is installed, any of these prompts will surface it:

- *"Review my signup form paywall using UX/UI psychology"*
- *"Apply behavioral design principles to this onboarding screen"*
- *"Check this pricing page against the 6 principles + 3 A/B-test patterns"*
- *"Redesign this booking screen — run it through UX psychology lenses first"*
