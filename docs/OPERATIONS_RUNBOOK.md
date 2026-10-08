# Operations Runbook
## Immediate controls
Global/tenant action kill switches; suspend campaign publishing, pause automation and disable outbound messaging without deleting data.
## Incident
Assess impact -> isolate tenant/provider -> revoke leaked tokens -> freeze jobs -> preserve evidence -> communicate -> restore -> postmortem.
## Provider outage
Queue safely with TTL and bounded retries; disable affected channel mutations; report degraded data freshness and reconciliation after recovery.
## Budget anomaly
Stop publisher, compare policy ledger and provider spend, revoke pending jobs, manually investigate and notify customer.
## Backup
Test database PITR and object restore regularly; record RPO/RTO targets before launch.
