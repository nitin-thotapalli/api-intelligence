# API Intelligence — Research & Development Roadmap

**Status:** Proposed experiments, not scheduled deliverables or completed engineering.

| Gate | Deliverable | Evidence required to progress |
| --- | --- | --- |
| 01 — Baseline | One task brief and manual source-research diary | Time and verification steps recorded; source requirements agreed |
| 02 — Source register | Small, source-linked catalog and field/rights schema | Every record has provenance, coverage and “last checked” date |
| 03 — Deterministic matcher | Rule-based shortlist with exclusion reasons | Hand-reviewed matching cases; no unauthorized sources selected |
| 04 — Validation | Sample extracts and primary-source reconciliation | Tests document units, dates, missing fields and conflicts |
| 05 — Decision packet | Human-readable shortlist, trade-offs and integration plan | Reviewer can reproduce a selection and see unknowns |
| 06 — Benchmark | Repeat against manual workflow and a changed source | Report time, errors, rework and maintenance effort transparently |
| 07 — Go/no-go | Product-scope decision | User value demonstrated without compromising reliability or rights |

## Minimum acceptance checklist

- [ ] A reproducible task specification and manually captured baseline exist.
- [ ] Every recommended provider has documented authority, access and restrictions.
- [ ] Essential required fields are tested on a small legitimate sample.
- [ ] Invalid, unavailable and unlicensed candidates are explicitly excluded.
- [ ] An independent reviewer can understand a recommendation without trusting an opaque model.
- [ ] A repetition test measures whether keeping the catalog current is worth the effort.
- [ ] No credentials or private provider responses are committed or publicly exposed.

## Measurement plan

Compare against the **same task done manually**. Record time to verified source bundle, required-field coverage, traceability, human-confirmed selection errors, and repeat-task maintenance time. Do not claim improved speed, accuracy or autonomous integration before a measured experiment.

## Out of scope until validated

Large public marketplaces, automatic API provisioning, OAuth and secrets custody, production SLAs, autonomous web/API execution and broad data resale.

## Decisions to revisit

- Who has the recurring problem and will use the result?
- Is an evaluated source packet valuable without live integration?
- What input categories require paid licenses?
- What evidence justifies adding agentic discovery rather than stronger manual tooling?
