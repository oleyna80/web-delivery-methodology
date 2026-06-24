# Work Block: WB-025 — Create Adapter Layer Contract and Index

## Status

Complete

## Lifecycle stage

Build

## Objective

Create the Adapter layer governance files under `docs/02_adapters/` without creating concrete tool adapters.

## Business reason

WB-024 planned the Adapter layer after WB-023 verified the Profile layer. The next step is to create a neutral adapter governance foundation before any concrete tool or execution-environment adapter becomes authoritative.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / adapter layer foundation

## Expected final result

Adapter layer foundation exists with README, adapter contract, and adapter index. The layer defines how future concrete adapters will map tools or execution environments to methodology roles, stages, profiles, templates, read/write permissions, evidence, and stop conditions.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-024-plan-adapter-layer.md` | Complete | Adapter-layer planning source |
| `PROJECT_MAP.md` | Current main | Planned path authority |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and independence authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk control authority |
| `docs/01_profiles/` | Verified | Profile compatibility authority |
| `docs/03_templates/` | Verified | Template compatibility authority |
| Owner approval in chat | Approved | Authority to execute WB-025 |

## Approved write-set

- `docs/02_adapters/README.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-025-create-adapter-layer-contract-and-index.md`

## Read-only scope

- `PROJECT_MAP.md`
- `docs/plans/WB-023-verify-initial-profile-layer.md`
- `docs/plans/WB-024-plan-adapter-layer.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/01_profiles/`
- `docs/03_templates/`

## Out of scope

- concrete adapters
- examples
- tool installation instructions
- runtime setup steps
- secrets, credentials, tokens, keys, private endpoints, or deployment credentials
- model routing or provider-selection policy
- application implementation instructions
- core/profile/template changes

## Acceptance criteria

- [x] `docs/02_adapters/README.md` exists and explains Adapter layer purpose, authority, boundaries, and status.
- [x] `docs/02_adapters/ADAPTER_CONTRACT.md` exists and defines the required structure and constraints for future concrete adapters.
- [x] `docs/02_adapters/ADAPTER_INDEX.md` exists and records that no concrete adapters are authoritative yet.
- [x] Concrete adapters remain deferred.
- [x] Examples remain deferred.
- [x] No core governance, profile, or template file is edited.
- [x] No secrets, credentials, model-routing policy, deployment credentials, installation commands, or runtime setup steps are added.
- [x] Changed files remain inside the approved write-set.

## Risks

- Adapter files may accidentally become operational setup instructions instead of methodology mappings.
- Adapter files may weaken separation of duties.
- Adapter files may over-authorize tool execution without Owner or Orchestrator approval.
- Adapter files may introduce vendor, model, provider, deployment, or credential assumptions too early.

## Checks and evidence

- Created exactly three adapter governance files.
- Compared changed files against approved write-set.
- Confirmed concrete adapters and examples were not created.
- Confirmed core/profile/template files remain unchanged by approved write-set scope.

## Stop conditions

- Adapter foundation requires changing core governance.
- Concrete adapters are needed before the adapter contract is reviewed and verified.
- The work requires storing operational configuration, secrets, credentials, or deployment details.

## Plan

1. Create adapter README.
2. Create adapter contract.
3. Create adapter index.
4. Check changed-file scope.
5. Close this Work Block and route to Review.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Planning -> Build | Approved WB-025 | Chat request: `переходим к WB-025 — Create Adapter Layer Contract and Index` | Create adapter governance foundation |
| 2026-06-24 | Orchestrator | Build | Work Block opened | `docs/plans/WB-025-create-adapter-layer-contract-and-index.md` | Create governance files |
| 2026-06-24 | Producer / Documentation Maintainer | Build | Adapter README created | `docs/02_adapters/README.md` | Continue contract/index |
| 2026-06-24 | Producer / Documentation Maintainer | Build | Adapter contract created | `docs/02_adapters/ADAPTER_CONTRACT.md` | Continue index |
| 2026-06-24 | Producer / Documentation Maintainer | Build | Adapter index created | `docs/02_adapters/ADAPTER_INDEX.md` | Check scope |
| 2026-06-24 | Orchestrator | Build | Scope check passed | changed-file comparison from WB-024 closeout to current main | Route to Review |

## Closeout

- Final status: Complete
- Artifacts created or changed: adapter governance foundation and WB-025 closeout
- Files changed:
  - `docs/02_adapters/README.md`
  - `docs/02_adapters/ADAPTER_CONTRACT.md`
  - `docs/02_adapters/ADAPTER_INDEX.md`
  - `docs/plans/WB-025-create-adapter-layer-contract-and-index.md`
- Checks run:
  - created exactly three adapter governance files
  - compared changed files from WB-024 closeout commit to current main
  - confirmed changed files remain inside approved write-set
  - confirmed no concrete adapter files were created
  - confirmed no examples were created
- Review verdict: pending
- Verification verdict: pending
- Deviations: none
- Residual risks:
  - adapter governance foundation requires independent Review
  - adapter governance foundation requires Verification before concrete adapters are created
  - concrete adapters remain deferred
  - examples remain deferred
- Required decisions: Owner approval to open follow-up Review
- Next owner/action: create `WB-026 — Review Adapter Layer Contract and Index`
