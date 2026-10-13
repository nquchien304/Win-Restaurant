# 03 — User Flows

**Status:** OPEN

Create one flow per user goal. Each flow must show success path, alternate paths, failure path, permissions, persisted state and observable feedback.

## Flow template

- **ID/name:**
- **Actor and goal:**
- **Preconditions:**
- **Trigger:**
- **Main path:**
- **Alternate paths:**
- **Failure paths / retry behavior:**
- **Data changed:**
- **Audit event:**
- **Acceptance criteria:**
- **Related rules/API/tests:**

## Minimum flows to resolve

1. Staff login/logout.
2. Configure menu and mark an item unavailable.
3. Map a QR code to a table; scan it from a phone on the real Wi-Fi.
4. Customer browse menu, customize item, edit cart and submit.
5. Duplicate submit / browser retry / timeout.
6. Staff receives and confirms order.
7. Kitchen sees items and updates status.
8. Item/order cancellation before and after sending to kitchen.
9. Table bill, discount/tax/rounding and payment recording.
10. Receipt printing, printer disconnected, reprint.
11. Close table/shift and reconcile totals.
12. Backup and restore.

## Lifecycle diagrams

Use Mermaid state diagrams or explicit transition tables for **Order**, **OrderItem**, **TableSession**, **Payment** and (if in scope) **InventoryMovement**. Do not use one ambiguous status field to represent multiple independent lifecycles.
