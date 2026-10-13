# 10 — API Contracts

**Status:** OPEN

Use a machine-readable contract (OpenAPI for HTTP APIs) before independently implementing clients and server endpoints: https://spec.openapis.org/oas/.

## Contract rules

For each endpoint specify:
- Method/path and purpose
- Caller/role and authorization
- Request schema, required fields and validation
- Response schema and status codes
- Error format and stable error codes
- Idempotency/retry semantics where relevant
- Transaction/side effects
- Concurrency expectations
- Related FR/BR/AC/test IDs
- Versioning/backward compatibility

## API design questions

- How is a table/QR session identified and validated?
- How does the server prevent client-supplied prices/totals from being trusted?
- How are duplicate submits distinguished from a new legitimate order?
- How are menu availability changes represented?
- Which actions require staff identity/permissions?
- What happens when response is lost after server commit?
- How do UI and server communicate printing status, if applicable?

## Draft contract artifact

Store the actual OpenAPI document under `api/openapi.yaml` once the first endpoints have been agreed. Validate it in CI when tooling is selected. Keep docs, server implementation and client types/tests aligned; a schema validator cannot replace human review of business semantics.
