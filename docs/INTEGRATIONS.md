# Integrations
## MVP
Meta Marketing API via official authorization; WhatsApp Business Platform with consent and approved template restrictions; payment processor checkout; email provider; analytics ingestion.
## Authentication
Use OAuth scopes required for stated actions, encrypted token storage, disconnect and revoke, rotation and refresh handling.
## Execution
Backoff and rate limiting per account/provider, idempotency keys, provider correlation IDs, webhook signature validation, periodic reconciliation and error categorization.
## Governance
Respect terms, content rules, ad targeting restrictions, platform review and account spending permissions. Never assume a sandbox capability is production-approved. Integrations should be feature-flagged.
