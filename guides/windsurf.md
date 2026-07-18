# Windsurf (formerly Codeium)

[Windsurf](https://codeium.com/windsurf) is an AI IDE from Codeium. It reads project context from **`.windsurfrules`** at the repository root (similar to Cursor's `.cursorrules` legacy file).

## Install

### Single rule file (simple)

```bash
# Strip Hermes frontmatter first
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > .windsurfrules
```

This makes the skill always-loaded for every chat in the project.

### Reference as a doc (for multi-purpose repos)

```bash
mkdir -p docs
cp SKILL.md docs/ux-ui-psychology.md

cat > .windsurfrules <<'EOF'
# Project Rules

When working on UI in `src/components/`, `web/`, or `app/` routes,
ALWAYS apply the UX/UI psychology rules in `docs/ux-ui-psychology.md`:
- 6 principles (smart defaults, goal gradient, reciprocity, IKEA/endowment, loss aversion, contrast)
- 3 A/B-test patterns (paywall, ride-hailing, booking)
- Ethical boundary: no fake timers, fabricated losses, or dark patterns
EOF
```

## Usage examples

In the Windsurf Cascade panel:

```
Review src/components/Paywall.tsx for UX psychology issues
```

Windsurf will apply the rules from `.windsurfrules` automatically.

## Windsurf specifics

- **`.windsurfrules`** is the only convention — there's no `.windsurf/rules/` directory equivalent yet.
- **Always loaded** — Windsurf doesn't support glob-based rule attachment like Cursor. The rules file is read at session start.
- **Global rules** — Windsurf supports per-user rules in Settings → AI Rules. These apply across all projects.
- **Cascade** — Windsurf's agent mode is called Cascade. It reads `.windsurfrules` on every Cascade session.
- **MCP support** — Windsurf supports MCP servers via Settings → MCP Servers, separate from rules.

## Migrating from Cursor

If you're moving from Cursor to Windsurf:

```bash
# Cursor's .cursor/rules/*.mdc → Windsurf's .windsurfrules
cat .cursor/rules/*.mdc > .windsurfrules
```

Note: Cursor's frontmatter (`description`, `globs`, `alwaysApply`) is ignored by Windsurf. Strip it when migrating.

## Recommended setup for UI-focused projects

For a repo where UX is the primary concern:

```bash
# .windsurfrules = full skill, always loaded
awk 'NR==1 && /^---/ {f=1; next} f && /^---/ {f=0; next} !f' \
  SKILL.md > .windsurfrules
```

For a multi-purpose repo:

```bash
# Short .windsurfrules + separate doc
cat > .windsurfrules <<'EOF'
# Project Rules

For UI work in src/components/, apply docs/ux-ui-psychology.md.
EOF

cp SKILL.md docs/ux-ui-psychology.md
```
