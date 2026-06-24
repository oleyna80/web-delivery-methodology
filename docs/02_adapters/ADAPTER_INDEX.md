# Adapter Index

## Purpose

This index records adapter governance files and future concrete adapters under `docs/02_adapters/`.

A file is not an authoritative adapter unless this index marks it as authoritative after Build, Review, and Verification.

## Governance files

| File | Purpose | Status |
| --- | --- | --- |
| `README.md` | Adapter layer purpose, authority, boundaries, and current status | Authoritative after WB-025 Review/Verification |
| `ADAPTER_CONTRACT.md` | Required structure and constraints for future concrete adapters | Authoritative after WB-025 Review/Verification |
| `ADAPTER_INDEX.md` | Index of governance files, authoritative adapters, and planned categories | Authoritative after WB-025 Review/Verification |

## Authoritative concrete adapters

Concrete adapters listed here are authoritative only within their stated limitations and only after Build, Review, and Verification evidence is recorded.

| Adapter ID | File | Status | Supported profiles | Supported stages | Supported roles | Max risk tier without extra controls | Required Owner approvals | Review WB | Verification WB | Limitations |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `REPOSITORY_CODING_AGENT` | `docs/02_adapters/REPOSITORY_CODING_AGENT.md` | Verified | `LOW_RISK_LANDING_PAGE`, `STANDARD_BUSINESS_WEBSITE`, `WEB_APPLICATION` | Implementation Planning, Build, Review, Verification, Release Handoff support, plus bounded documentation support for other stages | Producer, Builder, Specialist, Reviewer, Verifier, Orchestrator-support | Tier 1 | Required for release/deployment decisions, destructive actions, restricted actions, material residual risk, business-scope changes, sensitive or regulated work | `WB-030` | `WB-031` | Generic repository-aware coding environment only; no vendor/product/model/provider assumptions; subordinate to core governance, profiles, templates, and active Work Block |

## Draft concrete adapters

Draft adapters are not authoritative.

| Adapter ID | File | Status | Supported profiles | Supported stages | Supported roles | Max risk tier without extra controls | Required Owner approvals | Review WB | Verification WB | Limitations |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `CONVERSATION_ORCHESTRATOR` | `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md` | Draft | `LOW_RISK_LANDING_PAGE`, `STANDARD_BUSINESS_WEBSITE`, `WEB_APPLICATION` | Intake, Product Definition support, Architecture/UX/UI routing, Implementation Planning, Build coordination, Review evidence intake, Verification evidence intake, Release Handoff support, Improvement | Orchestrator-support, Producer, Specialist, conditional read-only Reviewer, conditional read-only Verifier | Tier 1 | Required for release/deployment decisions, destructive actions, restricted actions, material residual risk, business-scope changes, sensitive or regulated work, and role reassignment that could compromise independence | Pending | Pending | Generic conversational coordination environment only; not authoritative until Review and Verification pass; no repository write authority by default; no vendor/product/model/provider assumptions |

## Candidate adapter categories

These categories are planning candidates only. They are not concrete adapters.

| Candidate category | Purpose | Status | Notes |
| --- | --- | --- | --- |
| Design/Frontend Agent adapter | Map design-generation or frontend-focused environments to UI Design, Visual Review, and frontend Build support | Candidate | Must distinguish Design Authority, Visual Review, and Build roles |
| Connector/Repository API adapter | Map repository connector actions to read/write constraints, audit evidence, and Work Block file maintenance | Candidate | Must prevent unauthorized audit-trail mutation and uncontrolled writes |
| Local CLI Agent adapter | Map terminal or local-repository execution environments to bounded Build, Review, or Verification assignments | Candidate | Create only if distinct from repository coding adapter |

## Required index fields for future concrete adapters

Every concrete adapter entry must include:

- adapter ID;
- adapter file path;
- status;
- supported profiles;
- supported stages;
- supported roles;
- maximum supported risk tier without extra controls;
- required Owner approvals;
- Review Work Block;
- Verification Work Block;
- last reviewed date or Work Block;
- known limitations.

## Status values

Use these adapter status values:

- `Candidate` — planned category or planned adapter, not authoritative.
- `Draft` — file exists but has not passed Review.
- `Reviewed` — file passed Review but not Verification.
- `Verified` — file passed Verification and may be authoritative if listed as such.
- `Deprecated` — no longer recommended for new work.
- `Superseded` — replaced by another adapter.

## Concrete adapter entry template

```markdown
| Adapter ID | File | Status | Supported profiles | Supported stages | Supported roles | Max risk tier without extra controls | Required Owner approvals | Review WB | Verification WB | Limitations |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `[ID]` | `[path]` | `[status]` | `[profiles]` | `[stages]` | `[roles]` | `[tier]` | `[approvals]` | `[WB-ID]` | `[WB-ID]` | `[limits]` |
```

## Index maintenance rules

- Adding a concrete adapter requires a Work Block.
- Promoting a concrete adapter to authoritative requires Review and Verification evidence.
- Deprecating or superseding an adapter requires a Work Block and reason.
- This index must not list secrets, credentials, private endpoints, deployment credentials, provider policy, model routing, or runtime setup details.
- If an adapter conflicts with core governance, profiles, templates, or the active Work Block, do not use it; route to Orchestrator.

## Current next action

Review the `CONVERSATION_ORCHESTRATOR` draft adapter before Verification or authoritative use.
