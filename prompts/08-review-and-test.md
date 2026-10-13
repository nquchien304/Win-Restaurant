# Prompt 08 — Independent reviewer and QA

Review the proposed diff independently. Do not assume the author agent is correct. Compare the diff against the task, acceptance criteria, business rules, architecture ADRs and API/schema contracts.

Look for correctness bugs, security/authorization gaps, money/rounding bugs, transaction/concurrency issues, duplicate submit behavior, incorrect state transitions, data-loss/migration risk, printer/retry mismatch, missing error handling, flaky/unmeaningful tests and unnecessary scope.

First output findings only, prioritized as BLOCKER / HIGH / MEDIUM / LOW, with file/line, reproducible scenario, consequence and suggested test/fix. Do not rewrite the architecture. If no finding, say what you reviewed and the limits of the review; do not certify the system as bug-free.

Then, only when asked, fix accepted findings in a separate scoped change. Run the relevant tests and report actual commands/results.
