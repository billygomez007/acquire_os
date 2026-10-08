# Security Policy
Do not submit security vulnerabilities as public GitHub issues. Use a private maintainer security contact defined before external launch.
## Required security controls
- OIDC/SAML-capable authentication where applicable, MFA for administrators, short server-side sessions, rotate refresh tokens, revoke on sign-out.
- Least-privilege roles: owner, admin, marketer, analyst, sales, viewer, support and platform admin. Permission checks server-side for every route and job.
- Tenant scoping with RLS, deny-by-default authorization, negative cross-tenant tests, tamper-resistant audit trails.
- Encrypt transit via TLS and data at rest; KMS-managed encryption for provider refresh tokens; rotate and revoke on disconnect; secrets vault, never .env in repository.
- Per-action approval for campaign publication, budget increases, audience changes and outbound contact. Spend caps with server-side enforcement and emergency kill switch.
- Webhooks: verify provider signatures, enforce replay window, deduplicate, preserve integrity and redact PII.
- Protect uploads: content type allowlist, size cap, malware screening, signed object URLs, no public buckets, private-by-default.
- LLM output untrusted; schema validate, policy gate, allowlisted tools, no arbitrary URL fetching or shell execution, isolate retrieval from instructions.
- Consent-driven communications with opt-out, retention bounds and frequency limits. Explicit channel/platform compliance.
- CI dependency checks, static code analysis, secret scanning, IaC checks, unit/integration/permission tests. Maintain SBOM and patch process.
- CSP, secure cookies, CSRF protections, XSS defense, SSRF controls, strict CORS, secure headers and rate limiting.
## Incident response
Severity triage, containment, revoke credentials, stop automated actions, preserve audit and evidence, notify affected customers/regulators when legally required, conduct review and test corrective controls.
## Before production
External penetration test, abuse and privacy review, disaster recovery exercise, signing/branch protection, SSO/MFA requirements, documented on-call coverage and legal review.
