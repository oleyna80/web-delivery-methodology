# WB-029 — Create Repository Coding Agent Adapter

## Status

In Progress

## Lifecycle stage

Build

## Objective

Create the first concrete adapter file for repository-aware coding environments and add a non-authoritative Draft entry to `ADAPTER_INDEX.md`.

## Business reason

WB-028 selected the Repository Coding Agent adapter as the first concrete adapter because repository-aware coding environments are central to the methodology workflow and exercise the adapter contract's read/write scope, evidence, role mapping, risk-tier, and separation-of-duties rules.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / adapter build

## Expected final result

Repository Coding Agent adapter draft exists, is listed in `ADAPTER_INDEX.md` as non-authoritative `Draft`, and is ready for independent Review.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-027-verify-adapter-layer-contract-and-index.md` | Complete / `PASS` | Adapter governance verification gate |
| `docs/plans/WB-028-plan-first-concrete-adapter.md` | Complete | First concrete adapter planning source |
| `docs/02_adapters/README.md` | Current main | Adapter layer boundaries |
| `docs/02_adapters/ADAPTER_CONTRACT.md` | Current main | Concrete adapter structure authority |
| `docs/02_adapters/ADAPTER_INDEX.md` | Current main | Adapter index authority |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and independence authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls |
| `docs/01_profiles/` | Verified | Profile compatibility authority |
| Owner approval in chat | Approved | Authority to execute WB-029 |

## Approved write-set

- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-029-create-repository-coding-agent-adapter.md`

## Read-only scope

- `docs/plans/WB-027-verify-adapter-layer-contract-and-index.md`
- `docs/plans/WB-028-plan-first-concrete-adapter.md`
- `docs/02_adapters/README.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/01_profiles/`
- `docs/03_templates/`

## Out of scope

- vendors, products, model names, provider policy, account assumptions
- installation commands
- runtime setup steps
- deployment instructions
- secrets or credentials
- examples
- core/profile/template changes
- marking the adapter authoritative before Review and Verification

## Acceptance criteria

- [ ] `docs/02_adapters/REPOSITORY_CODING_AGENT.md` exists.
- [ ] Adapter follows `ADAPTER_CONTRACT.md` required section structure.
- [ ] Adapter status is `Draft`.
- [ ] Adapter is generic and contains no vendor/product/model/provider assumptions.
- [ ] Adapter preserves core role authority and separation of duties.
- [ ] Adapter preserves Work Block authority over actual read scope and write-set.
- [ ] Adapter preserves risk-tier controls and Owner approval requirements.
- [ ] Adapter defines evidence returned, stop conditions, limitations, and handoff format.
- [ ] `ADAPTER_INDEX.md` contains a non-authoritative Draft entry for the adapter.
- [ ] Adapter is not marked authoritative.
- [ ] No examples are created.
- [ ] No core/profile/template files are edited.
- [ ] Changed files remain inside approved write-set.

## Checks and evidence

- Create the adapter file.
- Add Draft index entry.
- Compare changed files against approved write-set.
- Confirm no examples are created.
- Confirm no core/profile/template files are changed.

## Stop conditions

- Adapter requires vendor/product/model-specific assumptions.
- Adapter requires installation/runtime/deployment instructions.
- Adapter requires secrets or credentials.
- Adapter requires changing core governance, profiles, or templates.
- Adapter cannot preserve separation of duties.

## Plan

1. Create `REPOSITORY_CODING_AGENT.md` as Draft.
2. Update `ADAPTER_INDEX.md` with a non-authoritative Draft entry.
3. Check changed-file scope.
4. Close this Work Block and route to Review.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Planning -> Build | Approved WB-029 | Chat request: `подтверждаю WB-029 — Create Repository Coding Agent Adapter` | Create draft adapter |
| 2026-06-24 | Orchestrator | Build | Work Block opened | `docs/plans/WB-029-create-repository-coding-agent-adapter.md` | Create adapter file |

## Closeout

- Final status:
- Artifacts created or changed:
- Files changed:
- Checks run:
- Review verdict:
- Verification verdict:
- Deviations:
- Residual risks:
- Required decisions:
- Next owner/action:
