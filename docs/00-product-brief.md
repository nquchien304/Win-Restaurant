# 00 — Product Brief

**Status:** OPEN — owner approval required  
**Owner:** Product owner/developer  
**Last reviewed:** YYYY-MM-DD

## One-sentence vision

A local-first restaurant operations system that lets staff manage tables, menu, orders, kitchen workflow, receipts and agreed reporting, while customers can order from a QR code at their table.

## Known context (verify each item)

- [PROPOSED] One restaurant/location.
- [PROPOSED] Installed on a computer at the restaurant; no public hosting/domain in the first release.
- [PROPOSED] Customer phones and the host computer use the restaurant LAN/Wi-Fi.
- [PROPOSED] One computer handles POS and receipt printing.
- [PROPOSED] Order volume is moderate, but simultaneous QR submissions must be safe.

## Product goals

1. Avoid lost, duplicated, or mispriced orders.
2. Make table/order status clear to staff and kitchen.
3. Print accurate bills/receipts reliably.
4. Keep data recoverable after a device or software failure.
5. Be operable by non-technical restaurant staff.

## Non-goals to consider

- Multi-branch cloud SaaS.
- Native mobile apps.
- Customer loyalty and CRM.
- Online payment gateway.
- Advanced accounting/e-invoice integration.
- Demand prediction/AI recommendations.

Confirm each as `DEFERRED`, `IN SCOPE`, or `OPEN`; do not assume.

## People and roles

| Role | Main jobs | Decisions still needed |
|---|---|---|
| Owner/Admin | Configure menu, users, reports, settings | Which reports and permissions? |
| Cashier/Staff | Open table, create/edit order, settle bill | Can staff void/discount/refund? |
| Kitchen | See incoming items and mark progress | Separate kitchen screen/printer? |
| Customer | Scan QR, browse menu, submit order | Can customer edit/cancel after submit? |

## Operating environment

- Host computer OS and hardware: OPEN
- Customer devices/browser support: OPEN
- Router/Wi-Fi/client isolation: OPEN
- Printer make/model/driver/protocol: OPEN
- Kitchen display or kitchen printer: OPEN
- Power/network interruption tolerance: OPEN
- Backup location and restore owner: OPEN
- Currency, tax and receipt/legal requirements: OPEN

## Success measures

Define measurable targets, for example:
- Percentage of test orders reaching the kitchen exactly once.
- Time from customer submit to staff/kitchen visibility.
- Receipt correctness across agreed scenarios.
- Restore test completed within an agreed recovery time.
- Staff can complete key flows using a short training guide.

## Release boundary

**MVP:** OPEN  
**Later:** OPEN  
**Out of scope:** OPEN

## Approval

- Product owner: OPEN
- Approved date: OPEN
