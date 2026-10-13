# Prompt 05 — Architecture, data model, API and ADR proposals (NO CODE)

Read approved product scope, requirements, rules and risk register. Do not implement anything.

Propose at least two plausible architecture options, including deployment on one local host with browser clients on restaurant Wi-Fi. Compare operational simplicity, concurrency, DB integrity, LAN access, printer integration, backup/restore, testability, security and maintenance. Avoid cloud requirements and microservices unless requirements justify them.

Produce/update proposals for:
- `docs/07-domain-model.md` (entities, relationships, invariants, historical snapshots, state ownership, deletion/archive)
- `docs/08-architecture.md` (component/deployment/network diagrams; trust boundaries; failure modes)
- `docs/09-security-and-privacy.md`
- `docs/10-api-contract.md`
- `docs/11-test-strategy.md`
- one ADR per major decision under `docs/adr/`

Do not choose a database just because it is familiar. Compare candidates against real concurrency, hosting, support, backup and maintenance needs. For SQLite, explicitly distinguish a database accessed by the application on the host from a database file placed on a network share; verify official constraints. For printer support, require a proof-of-concept using the actual model/connection/driver.

If HTTP APIs are appropriate, propose an OpenAPI contract for the first vertical slice. Include schemas, auth, errors, validation, duplicate-request behavior and compatibility. Mark proposals `PROPOSED`; list decisions needed from the owner. No code.
