# Aider

[Aider](https://aider.chat) is a terminal-based AI pair programmer. It reads project context from a few specific files:

- **`CONVENTIONS.md`** — project conventions Aider should follow (always loaded).
- **`.aider.conf.yml`** — Aider config (not for prose).
- **`docs/`** — can be added with `--read` flag.

Aider has no skill system — it uses always-loaded convention files and explicit file references.

## Install

### Option A: CONVENTIONS.md (always loaded)

```bash
cp SKILL.md CONVENTIONS.md
```

Good for **repos where every change should consider UX**.

⚠️ Aider loads `CONVENTIONS.md` on every session. For a multi-purpose repo, prefer Option B.

### Option B: Doc file + reference on demand

```bash
mkdir -p docs
cp SKILL.md docs/ux-ui-psychology.md
```

Then invoke Aider with `--read`:

```bash
aider --read docs/ux-ui-psychology.md
```

Or inside a session:

```
/add docs/ux-ui-psychology.md
```

### Option C: Repository-wide convention snippet

Add a short pointer in `CONVENTIONS.md`:

```markdown
# Conventions

When working on UI components in `src/components/`, apply the UX psychology
principles documented in `docs/ux-ui-psychology.md`.
```

## Strip the Hermes frontmatter

```bash
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > docs/ux-ui-psychology.md
```

## Usage examples

```bash
# Start aider with the skill preloaded
aider --read docs/ux-ui-psychology.md src/components/Paywall.tsx

# In an aider session
/add docs/ux-ui-psychology.md
"Review this paywall against the 6 principles and suggest changes"

# Headless / scripting mode
aider --read docs/ux-ui-psychology.md \
  --message "Redesign Onboarding.tsx using Goal Gradient + Reciprocity" \
  --yes-always
```

## Aider specifics

- **`--read <file>`** — adds a file to context for the whole session. Repeatable.
- **`/add <file>`** — same, but inside a session.
- **`--message`** — non-interactive one-shot mode (good for CI).
- **`--yes-always`** — auto-approve all changes (use with care).
- **No per-prompt rule selection** — Aider doesn't have Cursor-style glob-based rule attachment. Either `CONVENTIONS.md` is always on, or you `--read` the doc explicitly.
- **Token budget** — `--read` files count against context. For large skills, prefer a concise `CONVENTIONS.md` + on-demand `/add` of the full skill.
- **`.aiderignore`** — works like `.gitignore`; keep your `docs/ux-ui-psychology.md` un-ignored.
