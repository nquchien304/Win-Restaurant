# 15 — Open Questions & Risks

**Status:** OPEN

Keep a single canonical list to stop the agent repeatedly asking in chat or silently inventing answers.

## Open questions

| ID | Question | Why it matters | Options | Recommendation | Who decides | Needed by | Status |
|---|---|---|---|---|---|---|---|
| Q-001 | Which receipt printer model and connection will be used? | Determines printing integration | USB/driver, LAN, other | Run hardware spike | Owner | Architecture gate | OPEN |
| Q-002 | Can guest/customer phones reach the POS host over Wi-Fi? | QR menu may not load | Same LAN, separate VLAN, client isolation | Network proof-of-concept | Owner/network admin | Architecture gate | OPEN |
| Q-003 | Which database and deployment topology? | Data integrity/concurrency/backup | Compare supported relational options | Architect proposes, owner approves | Owner | Design gate | OPEN |
| Q-004 | Which bill, tax, discount and payment rules are required? | Financial correctness | Interview owner/accountant and verify law | Do not infer | Owner | Before bill implementation | OPEN |
| Q-005 | Is inventory in the MVP? | Large scope/data impact | Item stock vs ingredient/recipe inventory | Decide after use-case review | Owner | Scope gate | OPEN |

## Risk register

| ID | Risk | Likelihood | Impact | Mitigation | Trigger/monitoring | Contingency | Owner | Status |
|---|---|---|---|---|---|---|---|---|
| RK-001 | QR client cannot access host due to Wi-Fi isolation | Medium | High | Test actual network before architecture lock | Phone cannot reach health endpoint | Change network design with owner approval | Owner | OPEN |
| RK-002 | Printer integration discovered late | Medium | High | Test exact model early | Driver/protocol/proof print fails | Choose supported print path/hardware | Owner | OPEN |
| RK-003 | Duplicate order after retry | Medium | High | Specify and test idempotency/concurrency | duplicate test fails | Disable release until fixed | Developer | OPEN |
| RK-004 | Backup exists but cannot be restored | Medium | High | Scheduled restore drill | Restore verification fails | Block production handover | Developer | OPEN |
