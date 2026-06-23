# Work Block: WB-001 — Core Consistency Supplement

## Status

Complete

## Lifecycle stage

Build

## Objective

Apply bounded corrections from the Core Review Report to remove terminology drift, bootstrap ambiguity, and trivial README cleanup.

## Business reason

The core methodology must be internally consistent before profiles, adapters, templates, and examples are added as authoritative layers.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / core documentation supplement

## Expected final result

Core documents are internally consistent and ready for a separate read-only Verification step.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `README.md` | Current main | Authoritative entry point |
| `AGENTS.md` | Current main | Repository instructions |
| `PROJECT_MAP.md` | Current main | Authoritative file map |
| `docs/00_core/LIFECYCLE.md` | Current main | Canonical lifecycle |
| `docs/00_core/STATE_MACHINE.md` | Current main | Canonical execution states |
| `docs/00_core/STAGE_CONTRACT.md` | Current main | Stage contract requirements |
| `docs/00_core/WORK_BLOCK_CONTRACT.md` | Current main | Work Block contract |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Artifact ownership and planned paths |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role authority and separation of duties |
| `docs/00_core/APPROVAL_MATRIX.md` | Current main | Approval and sensitive decision authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk classification baseline |
| Chat Owner approval | Approved | Owner approval for this bounded supplement |
| Core Review Report | `SUPPLEMENT` | Reviewer / Documentation Analyst |

## Approved write-set

- `README.md`
- `AGENTS.md`
- `docs/00_core/STATE_MACHINE.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/plans/WB-001-core-consistency-supplement.md`

## Read-only scope

- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`

## Out of scope

- creating profiles
- creating adapters
- creating templates outside this Work Block
- creating examples
- adding tool-specific rules
- adding application code
- adding dependencies, secrets, deployment automation, or provider configuration
- changing methodology architecture

## Deliverables

- Terminology drift resolved in repository workflow wording.
- Non-canonical `released` state wording removed from the State Machine.
- Bootstrap rule added for repository-maintenance Work Blocks before the canonical template exists.
- Duplicate trailing README title removed.
- Work Block closeout recorded.

## Acceptance criteria

- [x] `AGENTS.md` no longer implies `Implementation` is a canonical lifecycle stage separate from `Implementation Planning` and `Build`.
- [x] `STATE_MACHINE.md` forbidden transitions use only canonical states or clearly named non-state actions.
- [x] `WORK_BLOCK_CONTRACT.md` explains how repository-maintenance Work Blocks may be created before the canonical template file exists.
- [x] `README.md` has no duplicate trailing title.
- [x] No profiles, adapters, examples, application code, secrets, dependencies, or deployment configuration are added.
- [x] Files changed remain within the approved write-set.

## Risks

- Overcorrecting core language may accidentally change the methodology architecture instead of only clarifying it.
- Creating the first Work Block before the canonical template exists may create precedent; the bootstrap rule must remain narrow.

## Checks and evidence

- Manual diff review against the approved findings.
- Search for unresolved terminology drift after edits.
- Verify changed files are within the approved write-set.

## Stop conditions

- A required change expands beyond the approved write-set.
- A fix requires creating profiles, adapters, examples, or new lifecycle architecture.
- A secret, dependency, deployment configuration, or application-code path is encountered.

## Plan

1. Record this Work Block in `docs/plans/` using the canonical inline template from `WORK_BLOCK_CONTRACT.md`.
2. Apply bounded documentation corrections for findings F-001, F-002, F-003, and F-005.
3. Re-read the changed files.
4. Record closeout and route to read-only Verification.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-23 | Owner | Review -> Build | Approved supplement execution | Chat approval for `WB-001` | Proceed within approved write-set |
| 2026-06-23 | Orchestrator | Build | Work Block opened | `docs/plans/WB-001-core-consistency-supplement.md` | Apply bounded supplement |
| 2026-06-23 | Producer / Documentation Maintainer | Build | Supplement applied | `README.md`, `AGENTS.md`, `docs/00_core/STATE_MACHINE.md`, `docs/00_core/WORK_BLOCK_CONTRACT.md` | Route to Verification |
| 2026-06-23 | Orchestrator | Build | Work Block closed | Acceptance criteria checked | Start read-only Verification Work Block |

## Closeout

- Final status: Complete
- Artifacts created or changed: repository-maintenance Work Block; repository instructions; state machine; Work Block contract; README cleanup
- Files changed:
  - `docs/plans/WB-001-core-consistency-supplement.md`
  - `README.md`
  - `AGENTS.md`
  - `docs/00_core/STATE_MACHINE.md`
  - `docs/00_core/WORK_BLOCK_CONTRACT.md`
- Checks run:
  - re-read changed files
  - searched for unresolved `Implementation step`, `during an Implementation`, lowercase `released`, and duplicate `# web-delivery-methodology`
  - searched for vendor/tool leakage terms: Codex, Claude, Antigravity, OpenAI, Next.js, n8n, Vercel, Docker, provider credentials, secrets
- Review verdict: `SUPPLEMENT`
- Verification verdict: pending separate read-only Verification
- Deviations: none
- Residual risks: concrete Stage Contracts are still not created; profiles/adapters should remain deferred until Verification passes and the next Work Block is approved
- Required decisions: Owner approval to start a separate read-only Verification Work Block
- Next owner/action: Orchestrator should open Verification for WB-001 results
