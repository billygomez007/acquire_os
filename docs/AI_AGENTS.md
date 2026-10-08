# AI Agents and Orchestration
## Agents
Business Analyst: extraction and verified company profile.
Research Agent: public/company-provided market evidence with citations and timestamp.
Strategy Agent: objective, channel, audience, forecast assumptions, budget proposal.
Creative Agent: compliant copy/assets and A/B hypotheses.
Campaign Planner: mapping to platform capabilities.
Optimization Agent: evaluate KPIs and draft bounded changes.
Lead Qualifier: approved intake questions and CRM summary.
Sales Follow-up: consent-aware, template-based sequences.
Attribution Analyst: separate observed, inferred and unknown results.
Risk/Compliance Reviewer: blocks restricted claims, policies and missing consent.
## Execution protocol
All agent outputs must match versioned JSON schemas with provenance. Tool intents enter a deterministic approval and policy engine: actor permission, tenant match, financial caps, legal/channel policy, data access scope and explicit user grant. The model cannot approve its own proposal.
## Prompt injection
Untrusted input may be evidence but never instructions. No secret retrieval, arbitrary outbound requests, changing budget caps or bypassing review because a document says so. See docs/security/PROMPT_INJECTION_DEFENSE.md.
## Evaluation
Golden cases, adversarial uploads, cross-tenant probes, bad-claim detection, spend safety tests and per-agent cost/latency dashboards. Track policy overrides and approval reversals.
