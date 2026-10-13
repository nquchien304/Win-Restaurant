# 02 — Scope & Priorities

**Status:** OPEN

Use MoSCoW with the product owner. “Must” must be necessary for the restaurant to use the release safely, not merely desirable.

## Candidate capabilities — not commitments

| Capability | Priority | Reason / evidence | Release |
|---|---|---|---|
| Login/roles | OPEN | | |
| Table management/status | OPEN | | |
| Menu/category/item/availability | OPEN | | |
| Table QR and customer menu | OPEN | | |
| Cart and order submission | OPEN | | |
| Staff order management | OPEN | | |
| Kitchen workflow | OPEN | | |
| Bill calculation/discount/tax | OPEN | | |
| Payment recording | OPEN | | |
| Receipt printing/reprint | OPEN | | |
| Daily/shift reports | OPEN | | |
| Audit history | OPEN | | |
| Inventory | OPEN | | |
| Backup/restore | MUST PROPOSE | Data safety | MVP candidate |
| Online payment integration | OPEN | External dependency/compliance | |

## MVP acceptance

The MVP must specify at minimum:
- The exact set of user journeys supported end-to-end.
- Explicitly excluded features and manual workarounds.
- Testable success criteria and a named approver.
- Performance/concurrency target based on expected usage.
- Backup and recovery method.
- Hardware/network compatibility proof.

## Scope change policy

Any new feature after the scope is approved must state: user value, data model/API impact, migration impact, new test cases, added operational burden and what gets delayed or removed to keep the release bounded.
