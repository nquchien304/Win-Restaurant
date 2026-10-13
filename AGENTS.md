# Agent Instructions — Restaurant System

## 1. Source of truth

Before work, read `README.md` and the smallest relevant set of files under `docs/`. Requirements and business rules outrank assumptions in examples. Approved decisions live in the docs and `docs/adr/`.

Use the status labels consistently:
- `OPEN`: not answered; do not silently guess.
- `PROPOSED`: AI suggestion awaiting human approval.
- `DECIDED`: approved and authoritative.
- `DEFERRED`: intentionally not part of the current release.

If an ambiguity blocks correctness, stop implementation and report the exact question plus options and consequences. If it does not block the current slice, record it and proceed without expanding scope.

## 2. Work mode

- For non-trivial tasks: inspect relevant files, restate scope, write a short plan, identify risks, then implement only after the plan is accepted.
- Prefer the smallest complete vertical slice over broad scaffolding or speculative abstractions.
- Do not build unrelated features, create multiple agents, or introduce microservices unless an approved ADR requires it.
- Do not alter approved business rules, public API contracts, database schema semantics, or architecture without proposing a change first.
- Avoid creating duplicate documentation. Update the canonical document rather than maintaining competing versions.

## 3. Safety boundaries

Do not, without explicit human approval:
- delete or rewrite user data, production data, or migration history;
- run destructive database commands or reset non-test environments;
- add external services, paid dependencies, analytics, telemetry, online payment, or cloud dependencies;
- change authentication/authorization boundaries;
- introduce or rotate secrets, change firewall/network settings, or disable security checks;
- add a dependency or change the database technology;
- silently change API compatibility or remove a feature.

Never commit secrets, passwords, real customer data, production database files, local absolute paths, or machine-specific credentials. Use synthetic test data.

## 4. Engineering rules

- Follow the stack, folder layout, naming, and dependency rules that are actually approved for this repo.
- Keep business rules in the appropriate application/domain layer, not duplicated across UI handlers.
- Validate untrusted input on the server. Calculate prices and totals on the server; never trust client-submitted totals or prices.
- Use transactions for multi-row business changes. Design duplicate submissions and retries explicitly for order/payment-sensitive operations.
- Persist money as a decimal-safe representation appropriate to the chosen stack; document currency and rounding rules.
- Use schema migrations; never rely on manual production-only schema edits.
- Log meaningful state changes without logging passwords, tokens, or payment-sensitive data.
- Keep order/payment histories auditable; do not silently hard-delete completed financial records.
- QR clients access data through the application API; do not expose the database file or database credentials to browsers/mobile devices.
- Never claim tests passed unless you actually ran them. Report commands and results, including tests not run.

## 5. Required loop for every code task

1. Read the task and relevant spec/ADR/API/data-model files.
2. Inspect the current implementation and tests; do not assume code structure.
3. State a short plan and list files expected to change.
4. Implement only the approved scope.
5. Add/update tests for changed behavior, including relevant failure cases.
6. Run focused tests, then broader checks appropriate to the change.
7. Review the diff for unintended changes, secrets, unrelated refactors, and contract drift.
8. Update documentation only if the behavior or contract changed.
9. Report: summary, files changed, tests and exact results, known gaps, and follow-up questions.

## 6. Definition of Done

A task is not complete just because code was written. It is complete when:
- approved acceptance criteria are met;
- relevant automated tests pass, or failures are explicitly reported;
- no known critical regression is introduced;
- API/schema/docs are consistent;
- deployment/data-migration implications are stated;
- the diff is scoped and reviewable.

## 7. Current project state

This repository is a blueprint until the owner approves a product brief and chooses a stack. Do not fabricate build commands, framework versions, database schemas, printer protocols, or deployment facts. Record unknowns in `docs/15-open-questions-and-risks.md`.
