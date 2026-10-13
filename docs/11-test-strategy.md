# 11 — Test Strategy

**Status:** OPEN

## Test pyramid / layers

- Unit tests: pure rules, calculation, transitions, validation.
- Integration tests: database constraints, transactions, migrations, repository behavior.
- API tests: permissions, schemas, error cases, duplicate requests, concurrent updates.
- UI/E2E tests: high-value end-to-end user journeys on supported browsers.
- Hardware acceptance tests: actual printer, paper size, encoding, reprint and failure behavior.
- Operational tests: installation, LAN access, restart, backup and restore.

## Required test cases before real use

- Create order from QR with correct server-calculated line totals.
- Invalid/unavailable item rejected safely.
- Retry does not accidentally duplicate a logical order.
- Concurrent orders for the last available item follow the approved policy.
- Invalid order-state transition rejected.
- Permissions prevent unauthorized price change/void/refund.
- Bill, discounts, taxes and rounding match owner-approved examples.
- Payment commit and receipt-print failure do not cause a second charge.
- Database migrations work from a clean install and from prior supported version.
- Backup restore produces a usable system and reconciled sample totals.

## Test data

Use fixtures with fictional menu items, tables and staff. Never use real customer data in tests or prompts.

## Commands and environment

Fill these only after the stack is selected:
- Install: OPEN
- Run locally: OPEN
- Unit tests: OPEN
- Integration tests: OPEN
- E2E: OPEN
- Lint/static analysis: OPEN
- Build/package: OPEN
- Migration validation: OPEN

## Reporting

Agent must list exact command, pass/fail, number of tests if available and checks not run. Do not accept “tests pass” without actual output.
