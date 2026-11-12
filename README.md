# API Intelligence

**Find the right data. Verify its source. Make it usable.**

API Intelligence is an independent product-research concept for discovering, evaluating, and organizing the APIs, datasets, and tools needed to answer a business or analytical question. It begins with a practical frustration: **before an analyst can test a hypothesis, they often spend hours locating data, checking its credibility, reconciling definitions, and connecting incompatible sources.**

## Why API Intelligence?

Consider an analyst beginning a company analysis in Project Matrix. They need financial statements, filings, price history, industry data, comparable companies, and perhaps operating indicators. Those inputs may live across public filings, data vendors, spreadsheets, websites, and APIs. Finding a source is only the beginning: **is it authoritative, current, licensed for this use, consistent with other sources, and usable in a repeatable workflow?**

The initial groundwork can consume more time than the work that matters most: forming hypotheses, understanding why performance changed, building models, and recommending what to do next.

API Intelligence asks: **Can we reduce the repetitive work of finding, assessing, and preparing reliable data and tools, so analysts and AI agents spend more time reasoning and less time assembling inputs?**

This is not only an API directory. The underlying problem is **source and tool intelligence**: choosing the right information and capabilities for a particular task, with provenance, constraints, and uncertainty visible.

## Who is it for?

The first user is a technically capable analyst or builder (including me) assembling data and tools for research or an AI workflow. Potential later users include finance researchers, analytics teams, and developers of tool-using agents. These audiences are hypotheses, not validated customer segments.

## The decisions it should improve

1. **Where should I get this information?** Identify candidate APIs, official filings, datasets, or tools for a specific question.
2. **Can I trust and use it?** Examine source authority, coverage, freshness, definitions, access, cost, and licensing.
3. **Which option fits this workflow?** Compare providers by required fields, granularity, reliability, integration effort, and restrictions.
4. **What is still missing?** Surface unavailable data, conflicting definitions, and checks that require a human.
5. **How can I repeat the work?** Produce a documented source map and integration plan rather than starting from scratch.

## Example: preparing a company research workflow

| Analyst need | Possible inputs to evaluate | Checks before use |
| --- | --- | --- |
| Financial performance | Company filings, annual reports, financial-data APIs | Reporting period, restatements, units, consolidated vs standalone |
| Market performance | Exchange data, market-data vendors | Symbol mapping, adjusted prices, timestamps, licensing |
| Peer comparison | Filings, company metadata, industry datasets | Peer definitions, business mix, currency, comparable periods |
| Operating context | Company disclosures, industry publications, relevant APIs | Definition consistency, source quality, missing observations |
| Model inputs | Verified outputs from the above | Lineage, transformations, assumptions, reproducibility |

**Proposed output:** a source register explaining what to use, why it was chosen, where it came from, how current it is, and what remains uncertain. This is groundwork for analysis—not a substitute for an analyst's judgment.

## Proposed workflow

1. **Describe the task:** e.g., compare five manufacturers' working-capital efficiency over five years.
2. **Translate the task into data requirements:** fields, geography, frequency, periods, entity identifiers, and precision.
3. **Discover candidate sources and tools:** official and commercial sources, documentation, endpoints, and access conditions.
4. **Evaluate suitability:** authority, completeness, update cadence, reliability, price, rate limits, security, and usage rights.
5. **Test and reconcile:** sample responses, schema checks, units, identifiers, duplicates, and conflicting values.
6. **Recommend a source/tool bundle:** ranked options with evidence, trade-offs, and missing capabilities.
7. **Prepare for integration:** mapping, validation rules, monitoring requirements, and a human-review checklist.

## What could make it intelligent?

- A **capability catalog** linking questions and required fields to relevant APIs and tools.
- A **source-quality framework** separating authoritative records from derived or unverified claims.
- **Schema and definition matching** across providers (for example, different meanings of revenue or open interest).
- **Evidence-backed comparisons** rather than recommendations based only on API descriptions.
- **Tool selection for AI agents** based on permissions, task fit, cost, and reliability.
- **Change detection** for deprecated endpoints, altered schemas, and stale data.

AI may assist with discovery, documentation search, and explanation; deterministic validation and explicit source references should remain central.

## Product thesis: a decision tool, not another API catalog

The customer problem is **choosing and operationalizing trustworthy data and tools for a defined task**. A directory listing thousands of endpoints would not, by itself, solve that problem.

| Existing alternative | What it does well | Remaining friction to investigate |
| --- | --- | --- |
| Web search and documentation | Broad discovery of possible sources | Repeated manual verification and comparison |
| Vendor directories or marketplaces | Provider and API listings | Often limited evidence of task-specific fit and data quality |
| Internal spreadsheets / wikis | Institutional memory | Staleness, inconsistent evaluation and difficult reuse |
| Manual analyst / developer judgment | Context-aware decisions | Time, inconsistent documentation and loss of provenance |

**Differentiation hypothesis:** Deliver a *task-specific, evidence-backed source selection and integration decision*, not an automatically generated list of fashionable tools. Whether that is actually valuable must be tested against doing the same work manually.

### Hypotheses to validate

| Hypothesis | Test | What would weaken or disprove it |
| --- | --- | --- |
| Source discovery is a material bottleneck | Time a manual analyst research task; log the stages | Most time is spent on interpretation rather than acquisition |
| Tool comparisons can be standardized | Evaluate the same requirements against multiple providers using a rubric | Real selection depends primarily on undocumented context |
| A structured source register improves reliability | Ask a reviewer to trace each key value to its origin and definition | Reviewers cannot reproduce source selection or still distrust it |
| Reuse reduces repeated research | Repeat a similar task with a maintained catalog | Maintenance exceeds saved effort or sources become stale |
| AI assistance helps, if grounded | Compare rule-based search with AI-assisted ranking on a human-reviewed set | AI adds unsupported claims or worsens accuracy |

### The core information model

A useful source record could contain **provider, capability, fields, geography, coverage, frequency, last verified date, documentation URL, licensing, authentication pattern, cost, rate limits, sample schema, data-quality checks, known gaps, and reviewer notes**.

A task record should contain its **question, required facts, acceptable freshness, output format, permitted sources, security constraints and evaluation criteria**. Matching these two records gives a reasoned shortlist. It should never be represented as automated verification without actually running the checks.

## How I would measure value

Metrics must connect the product mechanism to analyst outcomes, not just the size of the API catalog.

| Dimension | Candidate metric | Operational definition / guardrail |
| --- | --- | --- |
| Efficiency | Time to verified, usable data | Time from task brief to an independently reviewed usable input dataset; compare against a manual baseline |
| Completeness | Required-field coverage | Verified required fields available / total required fields |
| Trust | Source traceability rate | Material inputs with source URL, date, unit and definition / all material inputs |
| Correctness | Source-selection error rate | Human-reviewed incorrect or unusable recommendations / total evaluated recommendations |
| Repeatability | Rework and reuse | Time or checks needed to repeat a similar task after source updates |
| Practicality | Effective integration effort | Human hours needed to get from shortlist to a working, permitted sample |
| Guardrails | Security and licensing violations | Unauthorized access, exposed secrets or prohibited redistribution: **zero tolerated** in a prototype |

Proposed **north-star proxy:** *time to a verified, decision-ready source bundle*, subject to **no material source-selection errors**. This is a hypothesis for evaluation—not an existing product metric, benchmark, or achieved improvement.

## Explicit first release and out-of-scope work

**First release:** one financial/operating research question, a curated source catalog, a requirements-to-source matching rubric, sample-data validation and a reviewable recommendation report.

**Not yet:** an API marketplace, live credential vault, autonomous OAuth, production connectors, unrestricted agent tool execution, guaranteed current pricing, or universal data quality scores.

## Where it sits relative to other projects

API Intelligence is a **horizontal source-and-tool research idea**. It can stand on its own.

- **Project Matrix** asks how a business performs and what could improve it. It may use verified sources discovered here, but **it is not a required downstream product**.
- **F&O Analyst** is an independent **capital-markets and derivatives** research project. It may separately need licensed, well-described contract and market-data APIs.
- **Underwriting Engine** is an independent **underlying-asset / investment-thesis assessment** concept, currently more closely related to F&O Analyst than to Matrix.

There is **no shared running platform, no integration, and no mandated four-product sequence**. Shared data-source evaluation practices are a possibility, not an architectural dependency.

## First practical milestone

Start with one repeatable research question and a small number of sources. Document requirements, compare candidate APIs, test sample data, verify a few fields against authoritative references, and publish a reproducible source-selection report. Only then decide whether automated discovery or an agent is warranted.

**Possible measures of usefulness:** time to identify usable sources, coverage of required fields, verified-data accuracy, number of unresolved discrepancies, and effort to reproduce a workflow. These are proposed evaluation metrics, not achieved results.

## Boundaries and open questions

- Public data and private or paid data have different access and redistribution rights.
- No source is automatically trustworthy because it has an API.
- Freshness, accuracy, and completeness are separate dimensions.
- Credentials must remain server-side; never commit tokens or private data.
- No automated account connections, trading, or third-party actions are part of the initial scope.
- The first user workflow and actual time saved still need validation.

## Project documents

| Document | Purpose |
| --- | --- |
| [Original concept](docs/concept.md) | Earlier ideas, assumptions, and boundaries |
| [Proposed architecture](docs/architecture.md) | Initial technical components and data flow |
| [Development roadmap](docs/roadmap.md) | Possible milestones and acceptance checks |

These documents reflect earlier exploration; this README defines the current research direction.
