# Test Strategy
Unit: business rules, budget ledger, consent expiry, RBAC and validators.
Integration: tenant-scoped RLS, webhook signature/replay, OAuth refresh, publish idempotency, budget cap, queue retry, payment reconciliation.
E2E: tenant setup -> connected sandbox ad account -> reviewed proposal -> publish -> ingestion -> qualified lead -> booked appointment.
Security: forged token, privilege escalation, prompt injection, SSRF, mass assignment, consent bypass, fraudulent lead, cross-tenant lookup, replayed billing webhook.
AI evals: unsafe claims, source grounding, schema adherence, cost ceilings and missing-context deferral.
CI must fail when permission or spend-safety suites fail.
