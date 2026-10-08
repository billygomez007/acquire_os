# Architecture Essentials — Non-Negotiables
1. Multi-tenant design from day one; tenant scoping enforced in code and DB policies.
2. One source of truth for spend authorizations and action state.
3. AI may propose; deterministic policy authorizes; workers execute.
4. Human approval required for financial or outward-facing side effects until feature-flagged risk reviews authorize limited autopilot.
5. OAuth tokens encrypted; no user-supplied third-party passwords.
6. Consent receipt required before every automated outbound conversation.
7. APIs and webhooks idempotent and auditable.
8. Distinguish predictions from actual recorded business outcomes.
9. All actions must be stoppable with tenant/global kill switches.
10. Reversible migrations, recoverable database backups, reproducible deploys and environment separation.
11. Treat scraped pages, lead messages, files and tool results as untrusted inputs.
12. Security regression tests are release blockers.
See ARCHITECTURE.md, SECURITY.md and docs/security/.
