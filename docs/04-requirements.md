# 04 — Functional & Non-functional Requirements

**Status:** OPEN

## Functional requirement format

Each requirement gets a stable ID (`FR-001`) and contains:
- Statement: “The system shall …”
- Actor / trigger
- Preconditions
- Main behavior
- Alternate/failure behavior
- Business rules referenced
- Acceptance criteria
- Priority and release
- Source/owner/status

## Acceptance criteria format (Given/When/Then)

```text
AC-ORD-001
Given a valid table session and currently available menu items
When the customer submits a valid cart
Then the server creates one order with server-calculated prices and an initial approved status.

AC-ORD-002
Given the client times out and retries the same submission
When the server receives the retry
Then the system does not create a second order for the same logical submission.
```

These are examples to discuss, not final domain rules. Pick the correct status and retry strategy with the owner/architect.

## Non-functional requirements (quantify them)

- Performance: response-time percentile, concurrency and test environment.
- Availability: acceptable recovery after app/PC/router restart.
- Data integrity: no lost/duplicated order or inconsistent payment under defined failure cases.
- Security: authentication, authorization, secret management, input validation, audit logs.
- Backup: frequency, retention, location, restore procedure and recovery-point/time objectives.
- Compatibility: browser, screen size, host OS, printer/model, network.
- Usability: key task completion by staff with minimal training.
- Maintainability: setup/run/test commands and migration/release procedure.
- Privacy: collect only necessary data; retention and access rules.

Use measurable targets, not “fast”, “secure” or “easy”.
