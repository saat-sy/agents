# agents

Shared rules for Claude Code and Codex. `AGENTS.md` is always loaded and indexes the on-demand files in `rules/`.

## Layout
- `AGENTS.md`: always-on rules and the index of task triggers.
- `rules/docs/`: documentation and plan-writing rules.
- `rules/python/`: Python style and code structure.
- `rules/meta/`: how to add or change rules.

## Setup
Link both tools' global rule files to `AGENTS.md`:

```
ln -s ~/source/agents/AGENTS.md ~/.claude/CLAUDE.md
ln -s ~/source/agents/AGENTS.md ~/.codex/AGENTS.md
```

`AGENTS.md` refers to rules at `~/source/agents/rules/`. If the repo lives elsewhere, update those paths and the links.

## Editing
Edit rules only in this repo, never through the symlinks. Follow `rules/meta/rule-writing.md`.
