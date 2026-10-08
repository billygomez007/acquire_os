# Threat Model
## Protected assets
Ad account tokens, spend authorization, company data, customer PII, leads, creative assets, payment events and audit trail.
## Threat actors
External attacker, malicious tenant, rogue insider, compromised account, malicious lead, manipulated vendor content, compromised integration.
## Abuse scenarios and mitigations
Cross-tenant exfiltration -> RLS, object scoping, adversarial tests.
Unapproved spend -> immutable approval version, budget ledger, limits, kill switches.
Prompt injection -> untrusted content separation and typed tool intent, policy approval.
Unauthorized WhatsApp -> consent receipt and suppressions, provider-template controls.
Credential theft -> KMS, short token scopes, rotation and protected secrets.
Webhook forgery/replay -> signature and timestamp, dedup.
Fraudulent attribution -> source tagging and evidence provenance, no unqualified claims.
Billing fraud -> hosted checkout and signed webhooks.
SSRF/upload malware -> fetch allowlists, private IP denial, content scanning.
Insider access -> least privilege, break-glass auditing, periodic reviews.
## Residual risks
External provider outages, ad policy changes and model hallucinations remain possible; show uncertainty and retain manual controls.
