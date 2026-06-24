# WB-032 — Promote Repository Coding Agent Adapter

## Status

Complete

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

- [x] Adapter metadata status is promoted from `Draft` to `Verified`.
- [x] Adapter metadata references WB-030 as Review Work Block.
- [x] Adapter metadata references WB-031 as Verification Work Block.
- [x] Adapter file states it is authoritative only as listed in `ADAPTER_INDEX.md`.
- [x] `ADAPTER_INDEX.md` lists `REPOSITORY_CODING_AGENT` under authoritative concrete adapters.
- [x] `ADAPTER_INDEX.md` no longer lists `REPOSITORY_CODING_AGENT` as a Draft adapter.
- [x] Promotion cites Review and Verification evidence.
- [x] No adapter behavior is broadened.
- [x] No examples are created.
- [x] No core/profile/template files are edited.
- [x] Changed files remain inside approved write-set.

## Checks and evidence

- Review gate: WB-030 verdict `APPROVE`.
- Verification gate: WB-031 verdict `PASS`.
- Scope gate: changes limited to adapter file, index, and WB-032 file.
- Changed-file scope from WB-031 closeout commit to current `main` contains only:
  - `docs/02_adapters/ADAPTER_INDEX.md`
  - `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
  - `docs/plans/WB-032-promote-repository-coding-agent-adapter.md`

## Stop conditions

- Review verdict is not `APPROVE`.
- Verification verdict is not `PASS`.
- Promotion would broaden adapter capability.
- Promotion requires changing core governance, profiles, templates, or examples.
- Promotion requires vendor/product/model/provider assumptions or operational setup content.

No stop condition was triggered.

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
| 2026-06-24 | Documentation Maintainer | Release Handoff | Adapter metadata promoted | `docs/02_adapters/REPOSITORY_CODING_AGENT.md` | Update index |
| 2026-06-24 | Documentation Maintainer | Release Handoff | Authoritative index entry added | `docs/02_adapters/ADAPTER_INDEX.md` | Check scope |
| 2026-06-24 | Orchestrator | Release Handoff | Scope check passed | compare from WB-031 closeout to current `main` | Close Work Block |

## Closeout

- Final status: Complete
- Artifacts created or changed: Repository Coding Agent adapter promotion, Adapter Index authoritative entry, WB-032 closeout
- Files changed:
  - `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
  - `docs/02_adapters/ADAPTER_INDEX.md`
  - `docs/plans/WB-032-promote-repository-coding-agent-adapter.md`
- Checks run:
  - confirmed WB-030 Review verdict `APPROVE`
  - confirmed WB-031 Verification verdict `PASS`
  - promoted adapter metadata to `Verified`
  - recorded WB-030 and WB-031 in adapter metadata
  - moved adapter from Draft listing to Authoritative concrete adapters listing
  - confirmed `REPOSITORY_CODING_AGENT` no longer appears as a Draft adapter
  - compared changed files from WB-031 closeout commit to current `main`
  - confirmed changed files remain inside approved write-set
  - confirmed no examples were created by approved write-set scope
  - confirmed no core/profile/template files were changed by approved write-set scope
- Review verdict: WB-030 `APPROVE`
- Verification verdict: WB-031 `PASS`
- Deviations: none
- Residual risks:
  - adapter remains subordinate to core governance, profiles, templates, and active Work Block
  - actual use still requires a properly scoped active Work Block
  - examples remain deferred
- Required decisions: none
- Next owner/action: plan the next concrete adapter or begin using `REPOSITORY_CODING_AGENT` where it fits the active Work Block
