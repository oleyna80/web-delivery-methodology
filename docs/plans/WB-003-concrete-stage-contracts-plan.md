# Work Block: WB-003 — Concrete Stage Contracts Plan

## Status

Complete

## Lifecycle stage

Implementation Planning

## Objective

Decide the repository structure and next execution scope for concrete Stage Contracts before profiles, adapters, templates, or examples are added.

## Business reason

The core lifecycle is verified, but profiles and adapters need stable concrete Stage Contracts as their base authority. Without them, future layers may duplicate or reinterpret lifecycle rules.

## Role

Orchestrator / Planning Producer

## Profile

Repository maintenance / core documentation planning

## Expected final result

A bounded plan that selects the concrete Stage Contract structure, records rationale, and defines the next Work Block for implementation.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `README.md` | Current main | Entry point and current status |
| `PROJECT_MAP.md` | Current main | Authoritative file map and planned layers |
| `docs/00_core/LIFECYCLE.md` | Current main | Canonical lifecycle stages and gates |
| `docs/00_core/STAGE_CONTRACT.md` | Current main | Required Stage Contract fields and validation rules |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Canonical artifact ownership and planned template paths |
| `docs/plans/WB-002-core-consistency-verification.md` | Complete / PASS | Verification authority for core supplement |
| Owner approval in chat | Approved | Authority to create this planning Work Block |

## Approved write-set

- `docs/plans/WB-003-concrete-stage-contracts-plan.md`

## Read-only scope

- `README.md`
- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/plans/WB-001-core-consistency-supplement.md`
- `docs/plans/WB-002-core-consistency-verification.md`

## Out of scope

- creating concrete Stage Contract files
- editing `docs/00_core/LIFECYCLE.md`
- editing `docs/00_core/STAGE_CONTRACT.md`
- editing `PROJECT_MAP.md`
- creating profiles
- creating adapters
- creating templates
- creating examples
- adding tool-specific rules
- adding application code, dependencies, secrets, deployment automation, or provider configuration

## Deliverables

- Structure decision for concrete Stage Contracts.
- Rationale for the selected option.
- Proposed next Work Block with write-set and acceptance criteria.

## Acceptance criteria

- [x] The plan compares at least two viable structures.
- [x] The selected structure preserves canonical lifecycle authority.
- [x] The selected structure supports future profiles without duplicating lifecycle logic.
- [x] The selected structure keeps `docs/00_core/` tool-agnostic and vendor-neutral.
- [x] The next Work Block has a bounded write-set and excludes profiles/adapters/templates/examples.
- [x] No core methodology files are edited by this planning Work Block.

## Risks

- Creating too many files at once may make review and verification noisy.
- Creating only one compact file may be easier now but harder to maintain when profiles and adapters depend on specific stages.
- Stage Contract content may accidentally restate or fork the lifecycle instead of instantiating the reusable Stage Contract format.

## Checks and evidence

- Checked core lifecycle stage count and names.
- Checked required Stage Contract fields.
- Checked current project map planned layers.
- Checked verified residual risk from WB-002.

## Stop conditions

- The plan requires changing the canonical lifecycle.
- The plan requires introducing product/vendor-specific behavior into core.
- The plan requires creating profiles or adapters before concrete Stage Contract readiness is resolved.

## Plan

1. Compare concrete Stage Contract structure options.
2. Select the preferred structure for the next implementation Work Block.
3. Define `WB-004` write-set, deliverables, and acceptance criteria.
4. Record closeout and route to Owner decision.

## Options considered

### Option A — Single compact `docs/00_core/STAGE_INDEX.md`

Description:

Create one file containing compact concrete contracts for lifecycle stages 0–10.

Advantages:

- Low file count.
- Easier to create and review in one pass.
- Useful as a quick bridge before profiles.

Disadvantages:

- Can become a large, dense file.
- Harder to link one stage as a stable authority.
- Future profile work may need to reference sections instead of files.
- Higher risk of accidental cross-stage edits.

Verdict: acceptable as a temporary bridge, but weaker as a long-term canonical structure.

### Option B — Individual files under `docs/00_core/stages/`

Description:

Create one concrete Stage Contract per canonical lifecycle stage:

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

Advantages:

- Clear source of truth per stage.
- Better future references from profiles, templates, adapters, and examples.
- Easier targeted review and future updates.
- Preserves separation between stage definitions and profile-specific depth.

Disadvantages:

- More files in the initial implementation Work Block.
- Requires stronger consistency checks across stage files.
- May be too large for a single review if every contract is written in full detail.

Verdict: best long-term structure, but should be implemented with an index and strict consistency checks.

### Option C — Hybrid: `STAGE_INDEX.md` plus individual stage files

Description:

Create a compact index that maps all canonical lifecycle stages to individual concrete Stage Contract files.

Advantages:

- Combines navigability with modular authority.
- Gives future profiles a stable index and stable per-stage targets.
- Keeps `LIFECYCLE.md` as the canonical stage map while stage files instantiate the required contract fields.
- Reduces ambiguity about which file to read first.

Disadvantages:

- Slightly more structure than Option B alone.
- Requires keeping the index aligned with individual files.

Verdict: recommended.

## Decision

Use **Option C — Hybrid: `STAGE_INDEX.md` plus individual stage files**.

Rationale:

- `LIFECYCLE.md` should remain the canonical stage map, not a dense contract repository.
- `STAGE_CONTRACT.md` should remain the reusable contract standard, not the concrete implementation of all stages.
- Individual files give future profiles and adapters precise stable references.
- A compact index prevents discoverability problems and gives reviewers one place to verify stage coverage.
- This preserves the verified boundary that profiles, adapters, templates, and examples are deferred until the concrete core base is ready.

## Recommended next Work Block

```text
Work Block: WB-004 — Create Concrete Stage Contracts

Stage: Build
Objective: Create a concrete Stage Contract index and one concrete contract file for each canonical lifecycle stage 0–10.
Role: Producer / Documentation Maintainer
Expected result: `docs/00_core/STAGE_INDEX.md` and `docs/00_core/stages/*.md` exist and instantiate the required fields from `STAGE_CONTRACT.md` without changing lifecycle architecture.
Approved write-set:
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
Read-only scope:
- `README.md`
- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/plans/WB-003-concrete-stage-contracts-plan.md`
Out of scope:
- editing existing core contracts unless a separate supplement is approved
- creating profiles
- creating adapters
- creating templates
- creating examples
- adding tool-specific or product-specific rules
- changing lifecycle stages, state vocabulary, roles, artifact ownership, approval authority, or risk tiers
Risk tier: Tier 1 documentation build
```

## Proposed WB-004 acceptance criteria

- [ ] `STAGE_INDEX.md` lists stages 0–10 with exact names from `LIFECYCLE.md`.
- [ ] Every stage has one corresponding file under `docs/00_core/stages/`.
- [ ] Every stage file includes all required fields from `STAGE_CONTRACT.md`.
- [ ] Required inputs and outputs align with `LIFECYCLE.md` and `ARTIFACT_REGISTRY.md`.
- [ ] Approvers and assurance roles align with `APPROVAL_MATRIX.md` and `ROLE_CONTRACTS.md`.
- [ ] Failure routes align with `LIFECYCLE.md` and `STATE_MACHINE.md`.
- [ ] No profile-, adapter-, template-, tool-, vendor-, or implementation-specific behavior is added.
- [ ] No existing core files are modified unless Owner separately expands the write-set.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-23 | Owner | Verification -> Implementation Planning | Approved WB-003 | Chat request: `WB-003 — Concrete Stage Contracts Plan` | Create planning Work Block |
| 2026-06-23 | Orchestrator / Planning Producer | Implementation Planning | Plan complete | `docs/plans/WB-003-concrete-stage-contracts-plan.md` | Await Owner decision on WB-004 |

## Closeout

- Final status: Complete
- Artifacts created or changed: Concrete Stage Contracts Plan
- Files changed:
  - `docs/plans/WB-003-concrete-stage-contracts-plan.md`
- Checks run:
  - compared structure options against lifecycle, Stage Contract requirements, project map, and WB-002 residual risk
- Review verdict: not yet reviewed
- Verification verdict: not yet verified
- Deviations: none
- Residual risks:
  - `WB-003` is a planning artifact and has not independently reviewed or verified its own recommendation
  - concrete Stage Contracts still do not exist until `WB-004` is approved and completed
- Required decisions: Owner approval to start `WB-004 — Create Concrete Stage Contracts`
- Next owner/action: approve or revise the recommended `WB-004` scope
