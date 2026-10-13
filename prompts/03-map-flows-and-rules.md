# Prompt 03 — Map journeys, lifecycles and rules (NO CODE)

Read `docs/02-mvp-scope.md`, `docs/03-user-flows.md`, `docs/04-requirements.md` and `docs/05-business-rules.md`.

Model the actual approved journeys. At minimum evaluate QR order submission, staff order management, kitchen workflow, bill/payment, printing and recovery. Do not assume every candidate feature is in scope.

For Order, OrderItem, TableSession and Payment if they are in scope:
1. Propose explicit states and allowed transitions.
2. Define actor/permission, preconditions, side effects and audit event for every transition.
3. Define forbidden transitions.
4. Consider retries, duplicate requests, concurrent staff actions, stale prices, sold-out items and response loss after a server commit.
5. Map every rule to an acceptance/test ID.

Update docs only with proposals where approval is needed. Do not create SQL or application code. Flag contradictory statuses or rules instead of smoothing them over.
