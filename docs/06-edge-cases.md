# 06 — Edge Cases & Failure Analysis

**Status:** OPEN

For every high-risk flow, ask: what if it happens twice, late, out of order, concurrently, partially, or while the network/device fails?

## Order / QR

- Same submit button tapped twice.
- Request reaches server but response is lost; browser retries.
- Two phones submit the final available item simultaneously.
- Menu price or availability changes while cart is open.
- QR belongs to wrong, moved or closed table session.
- Malicious customer changes menu-item ID, price, quantity or table ID in request.
- Browser refreshes/back button resubmits.
- Phone disconnects while order is being submitted.
- Staff edits or cancels an order while kitchen is acting on it.

## Kitchen

- Order appears late or twice.
- Some items are ready while others are not.
- Item unavailable after submission.
- Order cancellation after kitchen started preparing.
- Kitchen display/printer goes offline.

## Bill / payment

- Partial payment; split by item/person/amount if required.
- Wrong amount/payment method; void/refund/correction.
- Two staff attempt to settle the same bill concurrently.
- Discount applied after a partial payment.
- Rounding and tax boundaries.
- Printer fails after payment commits; reprint must not charge again.

## Runtime / operations

- Backend crashes during transaction.
- Power loss while database writes occur.
- Disk full, clock/time-zone mismatch, backup corrupted.
- Router restarts / DHCP IP changes / guest isolation.
- Host restarts after an OS update.
- Printer unplugged, driver fails, paper runs out.
- Database migration interrupted.
- Restore a backup onto a clean machine.

## Risk record

| ID | Scenario | Impact | Likelihood | Prevention | Detection | Recovery | Test ID | Priority |
|---|---|---|---|---|---|---|---|---|
| RISK-001 | Duplicate order after retry | High | Medium | Defined idempotency strategy | Compare logical request/order IDs | Staff-visible status and audit | | OPEN |
