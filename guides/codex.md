# Codex CLI

[OpenAI Codex CLI](https://github.com/openai/codex) reads project context from `AGENTS.md` at the repository root (also supports `codex.md`, but `AGENTS.md` is the canonical name). It's the OpenAI-flavored counterpart to Claude's `CLAUDE.md`.

## Install

Codex context is **always loaded for the whole repo** — there's no per-skill gating like Claude's skills. Two approaches:

### Option A: Use AGENTS.md as the single source of truth

```bash
cp SKILL.md AGENTS.md
```

Good for **repos dedicated to UI work**. Codex will apply UX psychology to every task.

### Option B: Keep AGENTS.md short, reference this skill

If your repo has other concerns, write a thin `AGENTS.md` that points to the skill:

```markdown
# Project Agents

When working on UI in `src/components/`, `web/`, or `app/` routes,
ALWAYS apply the UX/UI psychology rules in `docs/ux-ui-psychology.md`:
- 6 principles (smart defaults, goal gradient, reciprocity, IKEA/endowment, loss aversion, contrast)
- 3 A/B-test patterns (paywall, ride-hailing, booking)
- Ethical boundary: no fake timers, no fabricated losses, no dark patterns
```

Then:

```bash
mkdir -p docs
cp SKILL.md docs/ux-ui-psychology.md
```

## Strip the Hermes frontmatter

Codex reads `AGENTS.md` verbatim. The YAML frontmatter will appear as plain text in context. Strip it:

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > docs/ux-ui-psychology.md
```

## Usage examples

```bash
# One-shot: review a paywall
codex exec "Review src/components/Paywall.tsx against the UX principles in docs/ux-ui-psychology.md"

# Full-auto: implement a redesign
codex exec --full-auto "Redesign the onboarding flow using Goal Gradient + Reciprocity. Commit when done."

# With worktree isolation
git worktree add -b ux/redesign-onboarding /tmp/onboarding main
codex exec --full-auto "Apply the 6 principles to the onboarding flow" \
  --workdir /tmp/onboarding
```

## Codex specifics

- **No partial-load mechanism.** `AGENTS.md` is always-on. Keep it focused.
- **Works with `codex exec` and `codex review`.**
- **`.codex/` directory** is for codex config, not skills. Don't put skills there.
- **`codex.md` is a legacy alias** — prefer `AGENTS.md`.
