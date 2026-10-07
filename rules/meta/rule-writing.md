# Rule writing

Rules live in `~/source/agents`, the single source of truth for every harness (Claude Code, Codex). Edit only there, never through `~/.claude/` or `~/.codex/`.

## Placement
- Applies to nearly every task: one bullet under "Always apply" in `AGENTS.md`. Always-loaded text costs tokens on every session, so add sparingly.
- Applies to a specific kind of task: a new file in the matching `rules/<domain>/` subfolder (`docs/`, `python/`, `meta/`), plus one index line in `AGENTS.md` naming the task trigger and the file. Create a new subfolder only for a new domain, such as a language or tool.
- Extending an existing topic: edit that file instead of adding a new one.

## Writing
- Before adding, read the existing rules and resolve overlaps or conflicts in place.
- One topic per file, named for its trigger (`python.md`, not `misc.md`). Heading first, no preamble.
- Short imperative bullets. Include a reason only when the rule is not self-evident.
- Plain markdown only: no harness-specific frontmatter, syntax, or tool names.
- Follow `rules/docs/source-of-truth.md`: state the current rule, keep no history or obsolete alternatives.

## Finishing
- Reread `AGENTS.md` and the index: every rules file has exactly one trigger line, and no line points to a missing file.
- Do not commit. Summarize what changed for the user to review.
