# Prompt 04 — Hostile reviewer / break the specification (NO CODE)

Act as three independent reviewers: (1) restaurant operations manager, (2) senior backend/database architect, (3) hostile QA/security engineer. Read the product, flows, requirements, rules, data model and architecture proposals.

Try to break the design. Look especially for:
- ambiguity and contradictory requirements;
- missing roles and authorization paths;
- invalid lifecycle transitions;
- duplicated or lost orders on retries/concurrency;
- stale/tampered prices and totals;
- payment/receipt mismatch;
- cancellation after kitchen work starts;
- printer failure after a bill/payment is committed;
- network isolation, host IP changes, outages and restore failure;
- unsafe data deletion, migrations, secrets or logs;
- scope creep and premature abstraction.

Output a ranked findings table: severity, scenario, consequence, affected docs/IDs, suggested resolution, decision owner, and whether it blocks coding. Do not fix decisions silently. Distinguish blockers from later improvements. No code.
