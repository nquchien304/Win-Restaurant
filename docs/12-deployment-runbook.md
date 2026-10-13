# 12 — Deployment & Operations Runbook

**Status:** OPEN

## Pre-install inventory

- Host PC make/model, OS/version, CPU/RAM/disk, user permissions.
- Router model, LAN topology, DHCP behavior, firewall and guest isolation.
- Printer make/model, USB/LAN/Bluetooth connection, driver, paper width, character support, cutter/cash drawer.
- Kitchen hardware and any barcode scanner/drawer if needed.
- Staff access and who owns maintenance.

## Mandatory proof-of-concept before architecture lock

1. Start a tiny local service on the intended host.
2. Access it from at least two actual phones on restaurant Wi-Fi.
3. Restart host/router and verify the documented URL/IP recovery process.
4. Simulate simultaneous submissions.
5. Print a sample receipt using the candidate method and exact printer model.
6. Simulate printer disconnected / no paper and verify no duplicate payment.
7. Create a backup and restore it on a clean/test environment.

## Runbook sections to complete

- Installation and version/configuration inventory.
- Initial admin creation and credentials handover.
- Database initialization/migrations.
- LAN address, firewall and phone access.
- Printer setup and test print.
- Daily start/close checks.
- Backup schedule, retention and off-device copy.
- Restore procedure and periodic drill.
- Upgrade, compatibility check and rollback/forward-fix.
- Troubleshooting: server down, can't scan/open URL, QR reaches wrong table, order absent/duplicate, printer failure, database unavailable, low disk space.
- Data export/decommissioning and secure deletion policy.

## Operational design rules

- “Installed” is not accepted until a fresh install has been tested.
- Backup is not accepted until a restore has succeeded.
- Printing is not accepted until actual output is checked on the chosen model.
- Never test destructive recovery procedures against the live data store.
