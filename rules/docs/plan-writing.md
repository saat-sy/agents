# Plan writing

Organize implementation work into a small number of substantial numbered plans ("Plan 1", "Plan 2", ...). Each plan delivers a coherent, independently usable, committable result. Choose boundaries around meaningful outcomes, not individual files, helpers, or line counts.

- Make each plan self-contained: relevant context, intended result, implementation work, and acceptance or verification checks.
- Put overall architecture context, shared decisions, and initial code/setup work in Plan 1. Add later context where needed; do not repeat the foundation in every plan.
- Group closely related tasks within a plan. A short task list is fine; do not make each task a separate approval step.
- State each plan's scope and outcome. Order plans so each builds on completed results. List prerequisites only when needed.
- Keep the document concise: organize existing detail instead of duplicating it across background sections and an execution checklist. Preserve requirements, metric definitions, and acceptance criteria.
- Use as many plans as the work needs, with no fixed count or line limit. Split a plan only when it holds unrelated outcomes or cannot leave the repository usable, not merely because it touches several files or is large.
- After each plan, the repository must remain usable, and its changes must be reviewable and ready for the user to commit without later plans. Apply the step-by-step execution rule (see `AGENTS.md`) at these plan boundaries.
