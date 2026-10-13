# 07 — Domain Model & Data Design

**Status:** OPEN

Do not start by generating SQL. First identify entities, ownership, lifecycle, invariants and history requirements.

## Candidate concepts to validate

- Restaurant configuration (even for one location, if needed)
- DiningTable / TableSession
- MenuCategory / MenuItem / ModifierGroup / ModifierOption
- Order / OrderItem / OrderItemModifier / OrderStatusHistory
- KitchenTicket or production status (if needed)
- Bill / Payment / PaymentAdjustment (only if the domain requires these distinctions)
- Employee / Role / Permission / Shift
- Discount / TaxRule / ServiceCharge
- InventoryItem / Recipe / InventoryMovement (only if in scope)
- AuditEvent

These are concepts, not a mandated schema. Do not create entities without a requirement; do not collapse distinct lifecycles merely to reduce table count.

## For every entity, document

- Purpose and owner
- Identity and uniqueness rule
- Attributes, types, nullability, units and defaults
- Relationships/cardinality
- Invariants/constraints
- Lifecycle / state transitions
- Historical snapshot requirements
- Deletion/archive policy
- Indexes justified by query patterns
- Migration/backfill requirements
- Access control and sensitive fields

## Database design checklist

- [ ] Money representation, currency, precision and rounding documented.
- [ ] Time zone and timestamp policy documented.
- [ ] Order item retains necessary historical values.
- [ ] Foreign keys and unique constraints enforce integrity.
- [ ] Concurrent updates and transaction boundaries considered.
- [ ] Duplicate request/settlement strategy documented.
- [ ] Migration and rollback/forward-fix strategy defined.
- [ ] Backup and restore tested.
- [ ] Test data is synthetic.

## Required diagrams

Provide ERD plus lifecycle state diagrams for Order, Payment and TableSession (if used). Explain the trade-offs before finalizing tables.
