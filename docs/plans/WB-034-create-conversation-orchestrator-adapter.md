# WB-034 — Create Conversation Orchestrator Adapter

## Status

Complete

## Lifecycle stage

Build

## Objective

Create the Conversation Orchestrator adapter file and add a non-authoritative Draft entry to `ADAPTER_INDEX.md`.

## Business reason

WB-033 selected the Conversation Orchestrator adapter as the next concrete adapter because the methodology needs a verified conversational coordination layer to plan Work Blocks, route roles, prepare prompts, receive evidence, and maintain next-action continuity without silently taking Builder, Reviewer, Verifier, Owner, or Release authority.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / adapter build

## Expected final result

Conversation Orchestrator adapter draft exists, is listed in `ADAPTER_INDEX.md` as non-authoritative `Draft`, and is ready for independent Review.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-033-plan-conversation-orchestrator-adapter.md` | Complete | Conversation Orchestrator planning source |
| `docs/02_adapters/ADAPTER_CONTRACT.md` | Current main | Concrete adapter structure authority |
| `docs/02_adapters/ADAPTER_INDEX.md` | Current main | Adapter index authority |
| `docs/02_adapters/REPOSITORY_CODING_AGENT.md` | Verified | Existing repository work adapter boundary |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and independence authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage authority |
| `docs/00_core/WORK_BLOCK_CONTRACT.md` | Current main | Work Block authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls |
| Owner approval in chat | Approved | Authority to execute WB-034 |

## Approved write-set

- `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-034-create-conversation-orchestrator-adapter.md`

## Read-only scope

- `docs/plans/WB-033-plan-conversation-orchestrator-adapter.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/RISK_TIERING.md`
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
- broad assistant behavior policy outside methodology work

## Acceptance criteria

- [x] `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md` exists.
- [x] Adapter follows `ADAPTER_CONTRACT.md` required section structure.
- [x] Adapter status is `Draft`.
- [x] Adapter is generic and contains no vendor/product/model/provider assumptions.
- [x] Adapter preserves core role authority and separation of duties.
- [x] Adapter treats chat history as evidence, not approval authority.
- [x] Adapter does not silently inherit repository write authority.
- [x] Adapter preserves Work Block authority over actual read scope and write-set.
- [x] Adapter preserves risk-tier controls and Owner approval requirements.
- [x] Adapter defines evidence returned, stop conditions, limitations, and handoff format.
- [x] `ADAPTER_INDEX.md` contains a non-authoritative Draft entry for the adapter.
- [x] Adapter is not marked authoritative.
- [x] No examples are created.
- [x] No core/profile/template files are edited.
- [x] Changed files remain inside approved write-set.

## Checks and evidence

- Created the adapter file.
- Added Draft index entry.
- Compared changed files against approved write-set.
- Confirmed no examples are created by approved write-set scope.
- Confirmed no core/profile/template files are changed by approved write-set scope.

## Stop conditions

- Adapter requires vendor/product/model-specific assumptions.
- Adapter requires installation/runtime/deployment instructions.
- Adapter requires secrets or credentials.
- Adapter requires changing core governance, profiles, or templates.
- Adapter cannot preserve role separation.
- Adapter grants Owner, Builder, Reviewer, Verifier, or Release authority by default.

No stop condition was triggered.

## Plan

1. Create `CONVERSATION_ORCHESTRATOR.md` as Draft.
2. Update `ADAPTER_INDEX.md` with a non-authoritative Draft entry.
3. Check changed-file scope.
4. Close this Work Block and route to Review.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Planning -> Build | Approved WB-034 | Chat request: `Подтверждаю переход к WB-034 — Create Conversation Orchestrator Adapter` | Create draft adapter |
| 2026-06-24 | Orchestrator | Build | Work Block opened | `docs/plans/WB-034-create-conversation-orchestrator-adapter.md` | Create adapter file |
| 2026-06-24 | Producer / Documentation Maintainer | Build | Draft adapter created | `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md` | Add Draft index entry |
| 2026-06-24 | Producer / Documentation Maintainer | Build | Draft index entry added | `docs/02_adapters/ADAPTER_INDEX.md` | Check scope |
| 2026-06-24 | Orchestrator | Build | Scope check passed | compare from WB-033 closeout to current `main` | Route to Review |

## Closeout

- Final status: Complete
- Artifacts created or changed: Conversation Orchestrator adapter draft, Adapter Index draft entry, WB-034 closeout
- Files changed:
  - `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md`
  - `docs/02_adapters/ADAPTER_INDEX.md`
  - `docs/plans/WB-034-create-conversation-orchestrator-adapter.md`
- Checks run:
  - created `CONVERSATION_ORCHESTRATOR.md` as Draft
  - added non-authoritative Draft entry to `ADAPTER_INDEX.md`
  - compared changed files from WB-033 closeout commit to current `main`
  - confirmed changed files remain inside approved write-set
  - confirmed no examples were created by approved write-set scope
  - confirmed no core/profile/template files were changed by approved write-set scope
- Review verdict: pending
- Verification verdict: pending
- Deviations: none
- Residual risks:
  - adapter requires independent Review
  - adapter requires Verification before it can become authoritative
  - examples remain deferred
- Required decisions: Owner approval to open follow-up Review
- Next owner/action: create `WB-035 — Review Conversation Orchestrator Adapter`
