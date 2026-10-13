# Prompt 01 — Discover the domain (NO CODE)

Act as a senior Business Analyst for a small restaurant. This task is discovery only. Do not write application code, SQL schema or select the tech stack.

Read `docs/00-product-brief.md`, `docs/01-domain-discovery.md` and `docs/15-open-questions-and-risks.md`.

Produce:
1. A domain overview in plain Vietnamese.
2. Actors and their goals/permissions.
3. The restaurant's end-to-end workflows from table open to order settlement and closing.
4. Terms that need precise definitions (table, table session, order, order item, bill, payment, kitchen ticket, shift, etc.).
5. Assumptions separated from observed facts.
6. An ordered list of open questions, including why each changes product/architecture/cost.
7. A research log with authoritative sources, URL and date for claims that need external verification. Prefer official docs, hardware manuals and current local legal sources; do not fabricate references.
8. Proposed MVP candidates and non-goals, clearly marked `PROPOSED`.

Do not silently answer owner-specific questions. Ask the questions in the document, not as a long interruption to this analysis. Mark each item `OPEN`, `PROPOSED` or `DECIDED`. End with what must be clarified before the next phase. No code.
