# Prompt Injection Defense
Threat surfaces: scraped websites, company PDFs, user-uploaded catalogs, inbound chat messages, competitor examples, tool outputs and third-party search snippets. Content is data, not authority.
Controls: system/developer policy cannot be overridden by retrieved content; schemas and allowlisted tools; no arbitrary execution/network; redact secrets and customer PII in LLM context; immutable approval/spend constraints; explicit provenance on claims; minimize tenant context; quarantine suspicious instructions; log decisions without PII; adversarial test corpus.
Example: uploaded PDF instructs the AI to increase daily ad spend or email tokens. AI must ignore the instruction, summarize only business facts and never produce an authorized action on this basis.
