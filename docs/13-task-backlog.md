# 13 — Task Backlog

**Status:** OPEN

## Backlog rules

Each task should fit in one focused agent run/review cycle where practical. Prefer vertical slices that deliver a working behavior across UI/API/domain/database rather than huge layer-only batches. Avoid tasks like “build the whole backend”.

## Suggested sequence (reorder after discovery)

1. Confirm product brief, users, scope and acceptance criteria.
2. LAN + printer + deployment technical spikes; record findings and ADRs.
3. Repository skeleton, local run command, test command, lint/build and CI.
4. Staff login/authorization slice (if required for MVP).
5. Menu read/display slice.
6. Table/QR identity and customer menu slice.
7. Customer cart and safe order submission slice.
8. Staff order queue and order lifecycle slice.
9. Kitchen workflow slice.
10. Bill calculation/payment recording slice.
11. Receipt print/reprint and printer-failure slice.
12. Basic reports/shift-close slice.
13. Backup/restore, installation and operations hardening.

This is a candidate sequence, not a commitment. Dependencies and MVP choices may change it.

## Task board

| ID | Feature/slice | Spec status | Dependencies | Risk | Estimate | Acceptance IDs | Status |
|---|---|---|---|---|---|---|---|
| T-001 | Discovery and open questions | OPEN | None | Medium | | | TODO |

## Task readiness gate

Do not mark a task `READY` unless scope, touched contracts, acceptance criteria, test plan, dependencies, known risks and rollback/data implications are understood.
