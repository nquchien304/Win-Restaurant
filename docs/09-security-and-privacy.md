# 09 — Security & Privacy

**Status:** OPEN

Use risk-based controls appropriate to a local business system. Local-only does not mean automatically safe: customer phones share the network and devices can be misconfigured or compromised.

## Minimum topics

- Threat model: customer phone, staff user, host PC, router, printer, backups, dependency supply chain.
- Authentication: staff accounts/PIN policy, session expiry, password storage if passwords are used.
- Authorization matrix for edit/void/discount/refund/menu/configuration/reports.
- Server-side validation and parameterized DB access.
- CSRF/XSS/cookie/session protections appropriate to chosen UI architecture.
- Rate limits or abuse protections for public-on-LAN QR endpoints.
- Secrets and environment configuration; never ship credentials in frontend assets.
- Audit log for sensitive state changes.
- Data minimization and retention; avoid collecting unnecessary customer personal data.
- Dependency updates and vulnerability handling.
- Backup encryption/access, physical access to host, restore drills.
- Log redaction: no passwords, access tokens or unnecessary payment/person data.

## Security acceptance criteria

Write testable criteria per risk. Use OWASP ASVS as a checklist source when relevant: https://owasp.org/projects/asvs. Choose an appropriate verification depth rather than blindly implementing every control.

## Authority boundaries

Business owner must approve role permissions, personal data collection/retention, financial correction policy and any tax/e-invoice/legal assumptions. Verify current legal requirements from authoritative local sources or a qualified professional; AI research is not a legal sign-off.
