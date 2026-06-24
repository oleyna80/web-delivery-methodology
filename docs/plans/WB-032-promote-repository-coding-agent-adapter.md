# WB-032 — Promote Repository Coding Agent Adapter

## Status

In Progress

## Lifecycle stage

Release Handoff

## Objective

Promote `REPOSITORY_CODING_AGENT` from non-authoritative Draft to verified authoritative adapter after Review and Verification passed.

## Business reason

`REPOSITORY_CODING_AGENT` passed independent Review in WB-030 and independent Verification in WB-031. The adapter index requires explicit listing after Build, Review, and Verification before a concrete adapter may be used as methodology authority.

## Role

Orchestrator / Documentation Maintainer

## Profile

Repository maintenance / adapter promotion

## Expected final result

`REPOSITORY_CODING_AGENT` is listed as a verified authoritative concrete adapter in `ADAPTER_INDEX.md`, and the adapter file metadata reflects its Review, Verification, and promoted status.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-029-create-repository-coding-agent-adapter.md` | Complete | Adapter build evidence |
| `docs/plans/WB-030-review-repository-coding-agent-adapter.md` | Complete / `APPROVE` | Review gate |
| `docs/plans/WB-031-verify-repository-coding-agent-adapter.md` | Complete / `PASS` | Verification gate |
| `docs/02_adapters/ADAPTER_INDEX.md` | Current main | Promotion/index authority |
| `docs/02_adapters/REPOSITORY_CODING_AGENT.md` | Draft | Candidate adapter being promoted |
| Owner approval in chat | Approved | Authority to execute WB-032 |

## Approved write-set

- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-032-promote-repository-coding-agent-adapter.md`

## Read-only scope

- `docs/plans/WB-029-create-repository-coding-agent-adapter.md`
- `docs/plans/WB-030-review-repository-coding-agent-adapter.md`
- `docs/plans/WB-031-verify-repository-coding-agent-adapter.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`

## Out of scope

- changing adapter behavior beyond promotion metadata/status
- changing core governance, profiles, templates, or examples
- adding vendors, products, model names, provider policy, account assumptions, installation commands, runtime setup instructions, deployment instructions, secrets, or credentials
- creating examples
- changing Review or Verification evidence

## Acceptance criteria

- [ ] Adapter metadata status is promoted from `Draft` to `Verified`.
- [ ] Adapter metadata references WB-030 as Review Work Block.
- [ ] Adapter metadata references WB-031 as Verification Work Block.
- [ ] Adapter file states it is authoritative only as listed in `ADAPTER_INDEX.md`.
- [ ] `ADAPTER_INDEX.md` lists `REPOSITORY_CODING_AGENT` under authoritative concrete adapters.
- [ ] `ADAPTER_INDEX.md` no longer lists `REPOSITORY_CODING_AGENT` as a Draft adapter.
- [ ] Promotion cites Review and Verification evidence.
- [ ] No adapter behavior is broadened.
- [ ] No examples are created.
- [ ] No core/profile/template files are edited.
- [ ] Changed files remain inside approved write-set.

## Checks and evidence

- Review gate: WB-030 verdict `APPROVE`.
- Verification gate: WB-031 verdict `PASS`.
- Scope gate: changes limited to adapter file, index, and WB-032 file.

## Stop conditions

- Review verdict is not `APPROVE`.
- Verification verdict is not `PASS`.
- Promotion would broaden adapter capability.
- Promotion requires changing core governance, profiles, templates, or examples.
- Promotion requires vendor/product/model/provider assumptions or operational setup content.

## Plan

1. Open WB-032.
2. Update adapter metadata and current status.
3. Update `ADAPTER_INDEX.md` authoritative adapter table.
4. Confirm changed-file scope.
5. Close WB-032.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Verification -> Release Handoff | Approved WB-032 | Chat request: `Переходи к WB-032 — Promote Repository Coding Agent Adapter` | Promote adapter after Review/Verification |
| 2026-06-24 | Orchestrator | Release Handoff | Work Block opened | `docs/plans/WB-032-promote-repository-coding-agent-adapter.md` | Update adapter/index |

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
