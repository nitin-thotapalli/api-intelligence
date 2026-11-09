# API Intelligence — Proposed Architecture

**Status:** Design hypothesis; no running system, licensed connectors, or measured results.

**Product boundary:** Answer a defined research/builder question with an auditable **source and tool selection packet**. Credentials, account connections and automatic downstream actions are explicitly out of scope for the first prototype.

```text
Task / analytical question
       ↓
Requirements & constraints (fields, definitions, geography, dates, freshness)
       ↓
Curated evidence-backed source / capability catalog
       ↓
Hard filters (rights, access, coverage, permissions, required fields)
       ↓
Candidate comparison (authority, quality, costs, effort, failure modes)
       ↓
Sample-data validation & human review
       ↓
Source register + recommended workflow + unresolved gaps
```

## Components and contracts

| Component | Input | Output / responsibility |
| --- | --- | --- |
| Task parser | Plain-language question and user constraints | Structured required data, tolerances and acceptance criteria |
| Source registry | Documentation, official endpoints, provider terms | Versioned descriptions, tested date, provenance, permissions, restrictions |
| Matching rules | Requirements + registry | Eligible sources and explicit reasons for exclusion |
| Evidence checks | Sample data, primary-source cross-checks | Coverage, consistency, timestamps, units and exceptions |
| Comparator | Validated candidates | Scored trade-offs, no unsupported universal “best API” |
| Analyst review | Sources, samples and exceptions | Accepted/rejected decision with rationale |
| Export | Approved decisions | Reproducible source list, schema mappings and integration checklist |

## Minimum research entities

- **Task:** question, decision, entities, period, location, required metrics, granularity, freshness, access constraints.
- **Source:** provider, official documentation, license, pricing/access tier (as-of date), cadence, field catalog and coverage.
- **Test:** request/sample identifier, timestamp, expected vs returned fields, units, mapping, result and reviewer.
- **Selection:** task, candidates, acceptance/rejection rationale, unresolved risks, version.

## Model and evaluation boundaries

- Prefer deterministic filters and evidence tests before LLM-powered explanation.
- Distinguish *stated provider capability*, *tested capability*, and *inferred capability*.
- Never send secrets to a language model or expose paid data without proper rights.
- The score should be interpretable and sensitive to use-case constraints; missing data must not silently score as zero risk.
- Track quality using the [README metrics](../README.md#how-i-would-measure-value), with a manual benchmark and independent review.

## First example

Evaluate sources for five years of consolidated company revenue, operating cash flow and peer comparison. Produce an evidence register showing access terms, units, coverage and validation results. This is deliberately narrower than agent tool orchestration.

## Open design decisions

1. Analyst-first or developer-first user cohort after the initial self-use case?
2. How should a curated catalog be refreshed and discrepancies adjudicated?
3. Can public data support a credible end-to-end pilot before paid sources?
4. How much source matching needs an LLM versus explicit rules?
5. What are the licensing and redistribution boundaries for any public output?
