# 05 — Business Rules

**Status:** OPEN

Use stable IDs (`BR-001`). Every rule must have an owner, rationale and test coverage.

| ID | Rule | Rationale | Enforcement layer | Acceptance/test IDs | Status |
|---|---|---|---|---|---|
| BR-001 | Server is authoritative for item price and totals | Prevent client tampering / stale prices | Domain/application | | PROPOSED |
| BR-002 | An order item records the price and item description applicable at order time | Menu changes must not rewrite historical bills | Domain/database | | PROPOSED |
| BR-003 | Order state changes must follow an explicit transition policy | Avoid impossible jumps | Domain/application | | OPEN |
| BR-004 | Completed payments must not be silently hard-deleted | Auditability | Application/database | | PROPOSED |
| BR-005 | Duplicate submission behavior is explicit and tested | Retries happen on networks | API/application | | PROPOSED |
| BR-006 | Every discount/void/refund has a defined permission and reason policy | Prevent misuse | Authorization/domain | | OPEN |
| BR-007 | Tax, service charge and rounding formulas are specified | Correct receipts | Domain | | OPEN |
| BR-008 | Sold-out behavior and orders already in progress are explicit | Kitchen/customer consistency | Domain | | OPEN |

## State transition table

| Aggregate | Current state | Action | Allowed? | New state | Preconditions | Side effects |
|---|---|---|---|---|---|---|
| Order | | | | | | |
| Order item | | | | | | |
| Table/session | | | | | | |
| Payment | | | | | | |

Do not implement transitions from status names alone. Specify who can perform the action and what happens to historical records, kitchen tickets, stock and totals.
