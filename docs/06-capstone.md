# Capstone: Financial Test Data & AI Engineering Platform
**Deliver one reproducible bank-like fictional workload.**

1. Build Customer → Account → Transaction related tables, valid and invalid scenarios.
2. Use GenRocket scenarios **if licensed**, document real runs; Python fallback explicitly separate.
3. Try MOSTLY AI SDK on fictional datasets and compare privacy/quality/utility.
4. Deterministic masking + relation-safe subsetting; validate zero orphan rows.
5. Land Delta tables, produce versioned Gold Copy and document clone type and dependencies.
6. Refresh with retry/idempotency tests; expose datasets to a `qa` schema, check permissions and cleanup.
7. CI/CD: pytest/sql assertions on PK/FK, schema, counts and privacy guarantees with deliberately failing test.
8. Governance: RACI, SLA, audit, failure runbook, cost/time benchmarks.
9. RAG/AI: fictional finance policy documents, citations, vector retrieval, agent boundary tests and evaluation cases.
10. Final 10-minute demo and architecture decision record: why GenRocket over other tools for this **specific requirement**.

**Success:** A new engineer can reproduce it from the README without private data or credentials.
