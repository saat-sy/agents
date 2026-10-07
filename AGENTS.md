# Rules

Always apply:
- Never commit, amend, or change git history unless the user explicitly asks. Leave finished changes for the user to review and commit.
- Work split into numbered plans: execute only the current plan. Report the result, then wait for explicit approval before starting the next. Approval of the overall plan is not approval of every step.
- Files state the current intended design only. Edit in place; no "previously", "supersedes", or obsolete alternatives.

Project-specific instructions override these where they conflict.

Read the matching file in `~/source/agents/rules/` before starting, only if the task involves:
- Writing or editing docs, specs, plans, or instructions (`.md`, `.rst`, `.txt`): `docs/source-of-truth.md`
- Writing or restructuring an implementation plan: `docs/plan-writing.md`
- Writing or editing Python: `python/python.md`
- Adding, changing, or removing a rule: `meta/rule-writing.md`
