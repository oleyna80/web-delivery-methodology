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

No concrete adapter is authoritative yet.

Concrete adapters must be created, reviewed, verified, and explicitly listed here before use as methodology authority.

## Candidate adapter categories

These categories are planning candidates only. They are not concrete adapters.

| Candidate category | Purpose | Status | Notes |
| --- | --- | --- | --- |
| Repository Coding Agent adapter | Map repository-aware coding environments to bounded Build, Producer, Review, or Verification assignments | Candidate | Must preserve separation of duties and exact write-set boundaries |
| Conversation Orchestrator adapter | Map conversational assistant environments to Orchestrator, Producer, Documentation Analyst, or planning-support roles | Candidate | Must not treat chat history as approval evidence |
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

Review and verify the adapter governance foundation created by WB-025 before creating concrete adapter files.
