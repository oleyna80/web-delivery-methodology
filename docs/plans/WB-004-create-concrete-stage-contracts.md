# Work Block: WB-004 — Create Concrete Stage Contracts

## Status

Complete

## Lifecycle stage

Build

## Objective

Create a concrete Stage Contract index and one concrete contract file for each canonical lifecycle stage 0–10.

## Business reason

Profiles, adapters, templates, and examples need stable concrete stage authority before they can safely specialize or map the lifecycle.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / core documentation build

## Expected final result

`docs/00_core/STAGE_INDEX.md` and `docs/00_core/stages/*.md` exist and instantiate the required fields from `STAGE_CONTRACT.md` without changing lifecycle architecture.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-003-concrete-stage-contracts-plan.md` | Complete | Planning authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Canonical lifecycle stages and gates |
| `docs/00_core/STAGE_CONTRACT.md` | Current main | Required Stage Contract fields and validation rules |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Canonical artifact ownership and planned template paths |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role authority and separation of duties |
| `docs/00_core/APPROVAL_MATRIX.md` | Current main | Approval and assurance authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls and escalation baseline |
| Owner approval in chat | Approved | Authority to execute this Work Block |

## Approved write-set

- `docs/00_core/STAGE_INDEX.md`
- `docs/00_core/stages/00_INTAKE.md`
- `docs/00_core/stages/01_PRODUCT_DEFINITION.md`
- `docs/00_core/stages/02_SOLUTION_ARCHITECTURE.md`
- `docs/00_core/stages/03_UX.md`
- `docs/00_core/stages/04_UI_DESIGN.md`
- `docs/00_core/stages/05_IMPLEMENTATION_PLANNING.md`
- `docs/00_core/stages/06_BUILD.md`
- `docs/00_core/stages/07_REVIEW.md`
- `docs/00_core/stages/08_VERIFICATION.md`
- `docs/00_core/stages/09_RELEASE_HANDOFF.md`
- `docs/00_core/stages/10_IMPROVEMENT.md`
- `docs/plans/WB-004-create-concrete-stage-contracts.md`

## Read-only scope

- `README.md`
- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/plans/WB-003-concrete-stage-contracts-plan.md`

## Out of scope

- editing existing core contracts unless a separate supplement is approved
- creating profiles
- creating adapters
- creating templates
- creating examples
- adding tool-specific or product-specific rules
- changing lifecycle stages, state vocabulary, roles, artifact ownership, approval authority, or risk tiers
- adding application code, dependencies, secrets, deployment automation, or provider configuration

## Deliverables

- `docs/00_core/STAGE_INDEX.md`
- Eleven concrete Stage Contract files under `docs/00_core/stages/`
- Work Block closeout with checks and residual risks

## Acceptance criteria

- [x] `STAGE_INDEX.md` lists stages 0–10 with exact names from `LIFECYCLE.md`.
- [x] Every stage has one corresponding file under `docs/00_core/stages/`.
- [x] Every stage file includes all required fields from `STAGE_CONTRACT.md`.
- [x] Required inputs and outputs align with `LIFECYCLE.md` and `ARTIFACT_REGISTRY.md`.
- [x] Approvers and assurance roles align with `APPROVAL_MATRIX.md` and `ROLE_CONTRACTS.md`.
- [x] Failure routes align with `LIFECYCLE.md` and `STATE_MACHINE.md`.
- [x] No profile-, adapter-, template-, tool-, vendor-, or implementation-specific behavior is added.
- [x] No existing core files are modified.

## Risks

- Contract files may restate lifecycle details inconsistently.
- A stage file may accidentally assign approval authority to a producer or builder.
- The initial contracts may be sufficient for core but still need review before profiles depend on them.

## Checks and evidence

- Direct file reads after creation.
- Keyword search for stage file coverage and vendor/tool leakage.
- Compare changed files against approved write-set.
- Route to independent Review after Build.

## Stop conditions

- A required change needs editing an existing core file.
- A required detail depends on profile, adapter, tool, vendor, or implementation-specific behavior.
- A stage contract requires changing lifecycle architecture or authority boundaries.

## Plan

1. Create `STAGE_INDEX.md`.
2. Create concrete Stage Contract files for stages 0–10.
3. Re-read created files and check coverage.
4. Close this Work Block and route to Review.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-23 | Owner | Planning -> Build | Approved WB-004 | Chat approval for `WB-004` | Create concrete Stage Contracts |
| 2026-06-23 | Orchestrator | Build | Work Block opened | `docs/plans/WB-004-create-concrete-stage-contracts.md` | Create index and stage files |
| 2026-06-23 | Producer / Documentation Maintainer | Build | Concrete Stage Contracts created | `docs/00_core/STAGE_INDEX.md`, `docs/00_core/stages/*.md` | Route to Review |
| 2026-06-23 | Orchestrator | Build | Work Block closed | Changed-file comparison and vendor/tool leakage search | Await Owner approval for Review |

## Closeout

- Final status: Complete
- Artifacts created or changed: Concrete Stage Contract index; concrete Stage Contract files for lifecycle stages 0–10; WB-004 closeout
- Files changed:
  - `docs/00_core/STAGE_INDEX.md`
  - `docs/00_core/stages/00_INTAKE.md`
  - `docs/00_core/stages/01_PRODUCT_DEFINITION.md`
  - `docs/00_core/stages/02_SOLUTION_ARCHITECTURE.md`
  - `docs/00_core/stages/03_UX.md`
  - `docs/00_core/stages/04_UI_DESIGN.md`
  - `docs/00_core/stages/05_IMPLEMENTATION_PLANNING.md`
  - `docs/00_core/stages/06_BUILD.md`
  - `docs/00_core/stages/07_REVIEW.md`
  - `docs/00_core/stages/08_VERIFICATION.md`
  - `docs/00_core/stages/09_RELEASE_HANDOFF.md`
  - `docs/00_core/stages/10_IMPROVEMENT.md`
  - `docs/plans/WB-004-create-concrete-stage-contracts.md`
- Checks run:
  - compared changed files from `WB-003` closeout commit to current main
  - confirmed only the approved index, 11 stage files, and WB-004 file were added
  - searched for vendor/tool leakage terms: Codex, Claude, Antigravity, OpenAI, Next.js, n8n, Vercel, Docker, provider credentials, secrets
- Review verdict: pending independent Review
- Verification verdict: pending
- Deviations: none
- Residual risks:
  - stage contracts have not yet received independent Review or Verification
  - some stage contracts may need tightening after reviewer checks against `LIFECYCLE.md`, `STAGE_CONTRACT.md`, `ARTIFACT_REGISTRY.md`, `ROLE_CONTRACTS.md`, and `APPROVAL_MATRIX.md`
- Required decisions: Owner approval to start Review Work Block for WB-004 output
- Next owner/action: create `WB-005 — Review Concrete Stage Contracts`
