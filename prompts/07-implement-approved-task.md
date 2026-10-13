# Prompt 07 — Implement one approved task

Implement only **[TASK ID + TITLE]**. Before editing, read `AGENTS.md`, the task, linked canonical docs, relevant ADRs/contracts and existing code/tests. Inspect before assuming.

Rules:
- Follow the approved architecture and business rules. No unrelated cleanup, feature creep or unapproved dependencies.
- Keep the change as small as possible while completing the entire approved vertical slice.
- Validate all untrusted input server-side. Do not trust client-supplied price/totals.
- Use transactions/constraints according to the approved data design; do not improvise a different idempotency or lifecycle policy.
- Add/update tests for success, validation, permission and relevant failure/concurrency cases.
- Do not run destructive DB commands or modify live data. Do not add secrets or real customer data.
- If a blocking ambiguity or conflict appears, stop, explain the exact conflict, propose options and do not silently pick one.

Workflow: brief plan → implement → run focused tests → run broader relevant checks → inspect diff → update docs if contract changed. Never claim a test passed unless you ran it.

Final report must include: behavior delivered, files changed, acceptance IDs, exact commands/results, checks not run, migration/deployment impact, remaining risks and questions. Do not move to another task.
