# OpenCode

[OpenCode](https://opencode.ai) is a provider-agnostic open-source coding agent. It reads project context from `AGENTS.md` at the repo root (same convention as Codex).

## Install

OpenCode context is **always loaded** — same tradeoff as Codex. Two approaches:

### Option A: AGENTS.md as the single source of truth

```bash
cp SKILL.md AGENTS.md
```

Good for **repos dedicated to UI work**.

### Option B: Reference as a doc

```bash
mkdir -p docs
cp SKILL.md docs/ux-ui-psychology.md

cat > AGENTS.md <<'EOF'
# Project Agents

When working on UI in `src/components/`, `web/`, or `app/` routes,
apply the UX/UI psychology rules in `docs/ux-ui-psychology.md`.
EOF
```

## Strip the Hermes frontmatter

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > docs/ux-ui-psychology.md
```

## Usage examples

```bash
# One-shot
opencode run "Review src/components/Paywall.tsx against docs/ux-ui-psychology.md"

# With file attachment
opencode run "Apply UX psychology to this onboarding redesign" \
  -f src/components/Onboarding.tsx -f docs/ux-ui-psychology.md

# Force a strong model for design work
opencode run "Redesign the booking screen using the 3 A/B-test patterns" \
  --model openrouter/anthropic/claude-sonnet-4

# Iterative session (background)
opencode  # then in TUI: paste your task
```

## OpenCode specifics

- **Provider-agnostic**: works with Anthropic, OpenAI, OpenRouter, local models. For UX review, prefer Claude Sonnet or GPT-4 — they reason well about human psychology.
- **`--thinking` flag** shows model reasoning — useful for UX reviews where you want to see *why* a principle applies.
- **Background mode + `process(action="poll")`** works well for long redesigns.
- **Multiple agents**: OpenCode has `build` and `plan` agents. For UX work, consider using `plan` first to generate a redesign plan, then `build` to implement.
