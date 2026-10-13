# 08 — Architecture Decision & LAN Design

**Status:** OPEN

## Constraints to verify

- One on-premises host runs the authoritative application and data store.
- Customer phones access a browser-based QR menu through the local network.
- The system should not require a public domain/cloud runtime for normal in-restaurant operation (confirm whether startup/login/licensing requires internet).
- Receipt printing may require a host-side print component, a browser print workflow, or a printer-specific integration; hardware proof-of-concept is mandatory before committing to one.

## Architecture candidates to compare

Have the architect compare at least two realistic options, for example:

1. Single deployable modular monolith + relational DB on host computer.
2. Web application plus separate local database service on the same host.

Avoid proposing microservices unless a demonstrated requirement justifies operational complexity. Compare deployment complexity, concurrency, backup/restore, maintenance, local-network behavior, printer integration, testability and cost.

## Decisions to document

- UI approach and supported browsers.
- Backend runtime and framework.
- Database engine and version.
- Application/database process topology.
- API style, versioning and error format.
- Authentication and staff authorization.
- QR/table session approach and abuse controls.
- Server-side price calculation and transaction boundaries.
- Printing approach and fallback/reprint behavior.
- Logging, health checks and diagnostics.
- Configuration/secrets storage.
- Database migrations.
- Backup/restore and update/rollback procedure.

## LAN threat and resilience checklist

- [ ] Host has stable LAN address via router reservation or documented equivalent.
- [ ] Firewall exposes only required ports to trusted local networks.
- [ ] Network is tested from real phones; client isolation is checked.
- [ ] QR client is untrusted: server validates table/session and every submitted field.
- [ ] No DB port/file/credentials are exposed to customers.
- [ ] Staff/admin functions require authentication and authorization.
- [ ] Retry and concurrent submissions are safe.
- [ ] Failure message and staff recovery procedure exist.
- [ ] Router changes/IP changes have a recovery path.

## Technology decision template

For each option: assumptions, pros/cons, failure modes, operational burden, compatibility evidence, cost, security, test approach, recommendation and decision owner. Record final decision in `docs/adr/`.
