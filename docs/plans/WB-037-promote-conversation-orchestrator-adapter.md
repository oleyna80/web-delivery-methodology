# WB-037 — Promote Conversation Orchestrator Adapter

## Status

In Progress

## Lifecycle stage

Release Handoff

## Objective

Promote `CONVERSATION_ORCHESTRATOR` from non-authoritative Draft to verified authoritative adapter after Review and Verification passed.

## Business reason

`CONVERSATION_ORCHESTRATOR` passed Review in WB-035 and Verification in WB-036. `ADAPTER_INDEX.md` requires explicit listing after Build, Review, and Verification before a concrete adapter may be used as methodology authority.

## Role

Orchestrator / Documentation Maintainer

## Inputs and authority

| Input | Status | Authority |
| --- | --- | --- |
| `docs/plans/WB-034-create-conversation-orchestrator-adapter.md` | Complete | Build evidence |
| `docs/plans/WB-035-review-conversation-orchestrator-adapter.md` | Complete / `APPROVE` | Review gate |
| `docs/plans/WB-036-verify-conversation-orchestrator-adapter.md` | Complete / `PASS` | Verification gate |
| `docs/02_adapters/ADAPTER_INDEX.md` | Current main | Promotion/index authority |
| `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md` | Draft | Candidate adapter |
| Owner approval in chat | Approved | Authority to execute WB-037 |

## Approved write-set

- `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-037-promote-conversation-orchestrator-adapter.md`

## Out of scope

- changing adapter behavior beyond promotion metadata/status
- changing core governance, profiles, templates, or examples
- adding vendor-specific, model-specific, setup, deployment, credential, or implementation content
- creating examples
- changing Review or Verification evidence

## Acceptance criteria

- [ ] Adapter metadata status is promoted from `Draft` to `Verified`.
- [ ] Adapter metadata references WB-035 as Review Work Block.
- [ ] Adapter metadata references WB-036 as Verification Work Block.
- [ ] Adapter file states it is authoritative only as listed in `ADAPTER_INDEX.md`.
- [ ] `ADAPTER_INDEX.md` lists `CONVERSATION_ORCHESTRATOR` under authoritative concrete adapters.
- [ ] `ADAPTER_INDEX.md` no longer lists `CONVERSATION_ORCHESTRATOR` as a Draft adapter.
- [ ] Promotion cites Review and Verification evidence.
- [ ] No adapter behavior is broadened.
- [ ] No examples are created.
- [ ] No core/profile/template files are edited.
- [ ] Changed files remain inside approved write-set.

## Checks and evidence

- Review gate: WB-035 verdict `APPROVE`.
- Verification gate: WB-036 verdict `PASS`.
- Scope gate: changes limited to adapter file, index, and WB-037 file.

## Plan

1. Open WB-037.
2. Update adapter metadata and current status.
3. Update `ADAPTER_INDEX.md` authoritative adapter table.
4. Confirm changed-file scope.
5. Close WB-037.

## Execution log

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Verification to Release Handoff | Approved WB-037 | Chat approval | Promote adapter after Review and Verification |
| 2026-06-24 | Orchestrator | Release Handoff | Work Block opened | `docs/plans/WB-037-promote-conversation-orchestrator-adapter.md` | Update adapter and index |

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
