# System Architecture
## Decision
Start as a TypeScript modular monolith with independently scaling workers, a shared relational database with strict tenant isolation, and event-backed outbox. Split services only once operationally justified.
## Components
Browser -> Web application -> API/BFF -> domain modules -> PostgreSQL.
API -> durable job queue -> workers -> external ad APIs, LLM gateway, messaging gateways and analytics.
Object storage holds uploaded brand assets with signed short-lived URLs. Redis supports queues/cache and non-authoritative rate limits.
## Modules
Identity and organizations; membership/RBAC; business profiles; creatives; strategies; approvals and policy; ad account connections; campaigns; budget ledger; leads and consent; communications; CRM; attribution; analytics; AI orchestration; billing; notifications; audit.
## Tenant isolation
Every customer-owned table carries organization_id. Repository query layer scopes by tenant; enforce PostgreSQL RLS and integration tests with malicious cross-tenant IDs. Storage object keys and worker jobs carry tenant context; external connections belong to a single tenant.
## Action plane
LLM produces typed proposal, NEVER direct external side effects. Policy engine validates actor, tenant, channel, approval, budget and consent; durable job queue executes idempotently; ledger and immutable audit events capture every action.
## Data plane
Events ingested from platforms/webhooks -> signature check -> deduplication -> normalization -> append-only raw events -> aggregates and attribution. Separate reported platform metrics from platform-independent first-party outcomes.
## Transaction model
Postgres source of truth; transactional outbox; workers retry with exponential backoff and dead-letter queue; idempotency keys for channel mutations, billing and messages.
## Availability
Health endpoints, point-in-time DB restore, encrypted backups, migrations with backwards compatibility, rolling deploys. Reject writes safely when dependencies fail.
## Boundaries
No ad-platform credentials sent to frontend or LLM. Payments via hosted payment processor (never store card data). Messaging providers only after opted-in channel-specific authorization.
## Service targets
Define SLO after beta benchmarks. Monitor worker backlog, webhook age, API p95 latency, successful campaign submissions, attribution delay and policy denials.
