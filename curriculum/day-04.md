# Day 04 · 2026-11-01 — Delta Lake transactions

> **Target:** Delta Lake transactions + **PII PHI PCI classification**. 
> **Active study budget:** 7 hours max (breaks extra). Days with an exam: use 2–3h only and rest. Stop if you have passed the acceptance tests.

## Why this matters
Today's Databricks skill makes the financial data platform more reliable or secure; today's TDM skill supports safe repeatable test environments. Do not equate passing a video with independent execution.

## 1. Databricks study — 90 min (EXACT locations)
1. **Open this specific pre-existing daily course:** [Old Bootcamp Day 04](https://github.com/tim5633/databricks-data-ai-engineering-bootcamp/blob/main/curriculum/day-04.md). Read its learning objective, **course/topic links**, lab and tests. This is a direct file link—not a general Academy search page.
2. **Read official feature reference:** [Databricks documentation](https://docs.databricks.com/aws/en/delta/). Use in-page heading/navigation for **Delta Lake transactions** and follow matching examples. The URL may be an official section landing page (not a pretend deep lesson).
3. **Company course (gated):** [Databricks Partner Academy](https://partner-academy.databricks.com/) → Search **Data Engineering** → find **Delta Lake transactions** in the syllabus. Company login and availability required; verify lesson section name in your account.
4. **Official exam specifications:** [Current exam catalog](https://www.databricks.com/learn/training/certification); use the relevant exam's up-to-date Exam Guide, not remembered weights.

**Notes to produce:** 5 bullets on core concepts, one SQL/Python/Spark snippet, one risk or cost trade-off.

## 2. Databricks lab — 90 min (follow in order)
1. Reproduce the worked example or main lab in [the exact original lesson](https://github.com/tim5633/databricks-data-ai-engineering-bootcamp/blob/main/curriculum/day-04.md) using fictional data.
2. Change an input (schema/volume/failed permission/invalid row/stream event) and predict expected impact.
3. Run it and capture actual output in `labs/day-04/db-evidence.md`.
4. Add a negative test; write the failing case and expected remediation.
5. Record where it lives in the architecture: generation, staging, Gold Copy, refresh, governance or governed AI.

## 3. TDM + product study — 60 min (EXACT locations)
1. Topic: **PII PHI PCI classification**.
2. Official entry: [GenRocket Flight School → authenticated Domains, Generators, Scenarios; do not assume public module URL](https://www.postgresql.org/docs/current/ddl-constraints.html).
3. Related vendor workflow: [GenRocket Flight School → authenticated Domains, Generators, Scenarios; do not assume public module URL](https://www.genrocket.com/flight-school-welcome/).
4. On the cited page use its **visible navigation/search** for the named concepts; if access denied, mark BLOCKED and use the public docs or offline Python/SQL equivalent. Paid vendors' exact in-app learning sections are not publicly verified.
5. Write a 150-word explanation: requirement → feature → security risk → operating owner.

## 4. TDM hands-on — 90 min
**Concrete task:** Create sensitivity register and lawful minimization decisions.
1. Work from fictional `customers(customer_id,email)`, `accounts(account_id,customer_id)`, `transactions(transaction_id,account_id,amount)` tables.
2. Preserve PK/FK relationships; add anti-join assertions for orphan accounts and transactions.
3. Implement the task in SQL/Python/notebook or accessible vendor UI; if you cannot access GenRocket, label Python generation **fallback, not GenRocket experience**.
4. Save one usable artifact: `labs/day-04/tdm-lab.sql`, `.py`, or `design.md`; include sample input/output and expected failure test.

## 5. Integration — 75 min
1. Add the day's result to a single end-to-end architecture: requirements → generators → masking/subset → Delta versioned Gold Copy → QA provisioning → tests → governance → AI evaluation.
2. Run 1 successful validation and 1 deliberately failing condition; record command/output.
3. Write 3 flashcards for certification and one design trade-off vs an alternative product/approach.
4. Commit or save the lab and link it in your progress notes.

## 6. Retrieval, reflection and assessment — 15 min
- [ ] Can explain **Delta Lake transactions** independently in 90 seconds.
- [ ] Completed **PII PHI PCI classification** task and named the artifact location.
- [ ] Can rerun successful path and show a captured negative test.
- [ ] Documented security/privacy impacts, plus one cost/performance or operational constraint.
- [ ] Updated [daily progress tracker](../docs/04-progress.md).

## If blocked or behind
Only three essentials: reproduce **one Databricks lab (90m)**; perform **one TDM task (90m)**; write findings and commit (20m). Carry reading forward. **Do not paste company materials, customer data, tokens or exam questions into this public repo.**
