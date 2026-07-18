# Gemini CLI

[Gemini CLI](https://github.com/google-gemini/gemini-cli) is Google's official terminal AI agent. It reads project context from `GEMINI.md` at the repository root (the Gemini equivalent of `CLAUDE.md` / `AGENTS.md`).

## Install

Like Codex and OpenCode, Gemini CLI context is **always loaded**. Two approaches:

### Option A: GEMINI.md as single source of truth

```bash
cp SKILL.md GEMINI.md
```

Good for **repos dedicated to UI work**.

### Option B: Reference as a doc

```bash
mkdir -p docs
cp SKILL.md docs/ux-ui-psychology.md

cat > GEMINI.md <<'EOF'
# Project Context

When working on UI in `src/components/`, `web/`, or `app/` routes,
apply the UX/UI psychology rules in `docs/ux-ui-psychology.md`:
- 6 principles (smart defaults, goal gradient, reciprocity, IKEA/endowment, loss aversion, contrast)
- 3 A/B-test patterns (paywall, ride-hailing, booking)
- Ethical boundary: no fake timers, fabricated losses, or dark patterns
EOF
```

## Strip the Hermes frontmatter

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > docs/ux-ui-psychology.md
```

## Usage examples

```bash
# Interactive
gemini
> Review src/components/Paywall.tsx against docs/ux-ui-psychology.md

# One-shot via prompt
gemini -p "Redesign the onboarding flow using Goal Gradient + Reciprocity"

# With @ context
gemini "@src/components/Onboarding.tsx Apply the 6 UX principles to this component"
```

## Gemini CLI specifics

- **`GEMINI.md` hierarchy**: Gemini CLI looks for `GEMINI.md` in: (1) current dir, (2) parent dirs up to root, (3) `~/.gemini/GEMINI.md` (global). All are concatenated.
- **`@file` syntax** — like Cursor, you can attach files inline.
- **`/context` command** — interactive session command shows what's loaded.
- **Tools and extensions** — Gemini CLI supports MCP servers via `.gemini/extensions/`.
- **`--model`** — for UX work, prefer `gemini-2.5-pro` over flash; psychology reasoning is weak on smaller models.

## Global install (across all projects)

```bash
mkdir -p ~/.gemini
# Concatenate this skill into your global GEMINI.md
cat SKILL.md >> ~/.gemini/GEMINI.md
```

⚠️ This makes UX psychology load on every Gemini session, regardless of project. Consider a dedicated `~/.gemini/GEMINI-UX.md` that you `@`-reference only when needed.
