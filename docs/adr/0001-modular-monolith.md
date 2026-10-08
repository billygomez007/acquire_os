# ADR-0001: Start with a Modular Monolith
Status: Accepted for initial implementation.
Context: Many domain workflows share transactional security, approval and budget state. Early microservices raise coordination and failure costs.
Decision: TypeScript modular monolith for API/domain, separately deployable workers and managed DB/queue. Domain modules expose interfaces; integrations via adapters and outbox.
Consequences: Faster iteration and end-to-end consistency; requires strict module boundaries and eventually partitioning of scale-heavy workers.
Revisit when team scale, compliance or measured traffic justifies extraction.
