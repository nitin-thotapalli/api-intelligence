# API Intelligence

**Find the right data. Verify its source. Make it usable.**

API Intelligence is an independent product-research concept for discovering, evaluating, and organizing the APIs, datasets, and tools needed to answer a business or analytical question. It begins with a practical frustration: **before an analyst can test a hypothesis, they often spend hours locating data, checking its credibility, reconciling definitions, and connecting incompatible sources.**

**Status:** Concept / research. No deployed product, validated integrations, or measured time savings are claimed.

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

## Relationship to the other projects

- **Project Matrix:** defines the business questions and uses verified financial, market, and operating inputs for company diagnosis and value-creation analysis.
- **F&O Analyst:** may use evaluated market-data sources to inspect contracts, prices, volatility, and portfolio risk.
- **Underwriting Engine:** may use vetted underlying-asset and contract data to support an auditable investment or risk assessment.

API Intelligence is the **data-and-tool discovery layer**, not the investment recommendation engine or the company analysis itself.

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
