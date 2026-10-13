# Prompt 09 — Release / deployment readiness review

Read the release scope, runbook, test strategy, migration notes, security document, risk register and actual build/test scripts. Do not make code changes unless a separate task is approved.

Assess these gates:
- clean install on target host;
- app startup and LAN access from actual customer phones;
- stable address/firewall/network segmentation assumptions;
- correct behavior under concurrent order submissions;
- staff authentication/authorization;
- exact printer output, print failure and reprint behavior;
- database migration from prior supported version;
- backup and successful restore drill;
- restart/power/network recovery;
- supported browser/device behavior;
- logs contain enough diagnostic detail without secrets/personal data;
- owner/staff handover, admin credential handover, update/rollback procedure.

For every item mark PASS / FAIL / NOT TESTED / NOT APPLICABLE and cite actual evidence. Do not infer PASS from documentation alone. Produce a ranked go/no-go list. Any unresolved high-impact data-integrity, payment, access-control, backup/restore or core-operation risk blocks release unless the owner explicitly accepts a documented mitigation.
