# API Contract (proposal)
Base /v1 with OpenAPI 3.1. All endpoints authenticated unless explicitly documented public and ratelimited. All mutable requests require authorization, tenant access and idempotency keys for provider actions.
- POST /organizations; GET /organizations/:id; POST /organizations/:id/invitations
- POST /business-profiles; GET/PATCH /business-profiles/:id
- POST /connections/meta/start; GET /connections; DELETE /connections/:id
- POST /strategies; GET /strategies/:id
- POST /creatives; GET /creatives/:id
- POST /campaign-proposals; POST /campaign-proposals/:id/submit-for-approval
- POST /approvals/:id/approve|reject (different authorized actor where required)
- POST /campaigns/:id/publish (server checks policy and proposal version)
- POST /campaigns/:id/pause; GET /campaigns/:id
- POST /leads; GET /leads; PATCH /leads/:id
- POST /consents; GET /consents/:id; POST /consents/:id/revoke
- GET /analytics/overview; GET /audit-events
Return RFC 9457-style problem details with safe error codes; pagination cursor and org context from validated auth, not a caller-trusted header.
