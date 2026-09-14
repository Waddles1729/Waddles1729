## Masanari Makino (Masa)

AI engineer at **Coadmap**, in Tokyo. Previously a data engineer at **Sansan**.

I came to LLM work through the layers underneath it — web and mobile applications,
then data platforms, then infrastructure — and I still work across all of them.
The part I care most about is the unglamorous half of shipping an AI feature:
making it measurable, making it reproducible, and making it survive the next
model upgrade.

### What I'm working on

**[evalgate](https://github.com/Waddles1729/evalgate)** — a regression gate for LLM
applications. Score a feature against a golden dataset, diff it against a
committed baseline, and fail the build when it gets worse. Nine scorers
(deterministic, embedding-based, and LLM-as-judge including the RAG triad),
cached model calls so it is affordable on every pull request, and a shipped
example that runs offline with no API key.

```
score 0.442  (-0.527 vs baseline 0.969)

gate: FAIL
  ✗ must-pass cases failed: cancel-billing-period, medical-refusal, legal-refusal
  ✗ overall score fell by 0.527, over the allowed 0.020
```

**[querygate](https://github.com/Waddles1729/querygate)** — a read-only SQL MCP
server. Give an agent a database without giving it the keys: a tokenising guard
that refuses writes (including the ones hidden inside a CTE), tables the policy
hides from introspection entirely, column masking applied on egress so
`COUNT(DISTINCT email)` still returns the true number, and an audit trail that
records the refusals too. SQLite and Postgres; the demo needs neither a database
nor a credential.

```
name             email                   phone          city
Mei Tanaka       [redacted]@example.com  *********1667  Sendai

3 row(s) · 1ms · masked by policy: email, phone

Query refused: only SELECT statements are allowed; this one starts with DROP
Query refused: not permitted to read: employee_salaries
```

### What I do day to day

- **LLM systems** — LangGraph multi-agent architectures, RAG, knowledge graphs
  (Neo4j), and the evaluation loop around them: golden datasets, LLM-as-judge,
  RAGAS, tracing with Langfuse / LangSmith.
- **Forward deployed engineering** — sitting with a client, turning their
  business problem into requirements, and taking it through to production.
- **Full stack** — Ruby on Rails + GraphQL, Python + FastAPI, React +
  TypeScript, Kotlin.
- **Data platforms** — built a company-wide platform on BigQuery + Looker at
  Sansan: pipelines, dashboards, and the platform itself as an internal product.
- **Infrastructure** — GKE Autopilot, ArgoCD, Terraform Cloud, Google Cloud.
- **AI-assisted development tooling** — MCP servers, automated PR review, LLM
  quality gates in pre-commit.

### Background

| | |
| --- | --- |
| **Coadmap** | AI engineer · 2026– |
| **Sansan** | Data engineer / software engineer · 2023–2026 |
| **Milldea** | Engineer · 2021–2023 |
| **Datack** | Engineer · 2018–2021 |
| **Keio University** | M.Eng, Open and Environmental Systems · virtualization for embedded systems security |

### Elsewhere

[LinkedIn](https://www.linkedin.com/in/masanari-makino-817294243) ·
[Wantedly](https://www.wantedly.com/id/masanari_makino)

Open to contract work on evenings and weekends — fully remote, asynchronous,
around 10–20 hours a week. LLM evaluation and RAG systems, backend and
infrastructure, or data platform work.
