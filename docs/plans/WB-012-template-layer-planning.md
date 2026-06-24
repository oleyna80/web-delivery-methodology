# Work Block: WB-012 — Template Layer Planning

## Status

Complete

## Lifecycle stage

Implementation Planning

## Objective

Plan the next methodology layer: canonical templates under `docs/03_templates/`, based on the verified core Stage Contracts and `ARTIFACT_REGISTRY.md` planned template paths.

## Business reason

The core lifecycle, stage contracts, and wording corrections have passed Review and Verification. The next useful layer is templates, because profiles, adapters, and examples need stable artifact structures before they can be created safely.

## Role

Orchestrator / Documentation Planner

## Profile

Repository maintenance / methodology planning

## Expected final result

A bounded implementation plan for creating the initial template layer without adding profiles, adapters, examples, tool-specific behavior, or product-specific behavior.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Canonical artifact types and planned template paths |
| `docs/00_core/STAGE_CONTRACT.md` | Current main | Stage contract structure authority |
| `docs/00_core/WORK_BLOCK_CONTRACT.md` | Current main | Work Block template authority |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and ownership authority |
| `docs/00_core/APPROVAL_MATRIX.md` | Current main | Approval authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls |
| `docs/plans/WB-011-verify-build-stage-risk-wording-correction.md` | Complete / `PASS` | Verification gate for the last core wording correction |
| Owner approval in chat | Approved | Authority to plan the template layer |

## Approved write-set

- `docs/plans/WB-012-template-layer-planning.md`

## Read-only scope

- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `PROJECT_MAP.md`

## Out of scope

- creating actual template files
- editing existing core governance files
- creating profiles
- creating adapters
- creating examples
- adding tool-specific, vendor-specific, framework-specific, product-specific, or application-specific behavior
- changing lifecycle architecture, state vocabulary, role authority, approval authority, artifact ownership, or risk tiers

## Current repository facts

- `PROJECT_MAP.md` lists `docs/03_templates/` as a planned layer for canonical input, output, review, and handoff templates.
- `ARTIFACT_REGISTRY.md` lists planned template paths and explicitly states that those paths do not become authoritative until an approved template Work Block creates them.
- The verified core stage set is sufficient to create templates without changing core lifecycle architecture.

## Template layer decision

Create the initial template layer as thin canonical Markdown skeletons, not as product examples.

The first template build should create files only for the artifact types already listed in `ARTIFACT_REGISTRY.md`. Each template should:

- preserve canonical artifact ownership;
- include artifact status metadata;
- include inputs and authority;
- include acceptance criteria or review criteria where relevant;
- include evidence and decision sections where relevant;
- avoid product-, tool-, vendor-, framework-, deployment-, or application-specific assumptions;
- remain usable by future profiles without requiring profile-specific content now.

## Proposed template paths for the first build

The first Build Work Block should create these paths from `ARTIFACT_REGISTRY.md`:

- `docs/03_templates/intake/PROJECT_INTAKE.md`
- `docs/03_templates/product/PROJECT_BRIEF.md`
- `docs/03_templates/architecture/SOLUTION_BRIEF.md`
- `docs/03_templates/ux/UX_SPECIFICATION.md`
- `docs/03_templates/design/DESIGN_SPECIFICATION.md`
- `docs/03_templates/design/DESIGN_REVIEW.md`
- `docs/03_templates/implementation/IMPLEMENTATION_PLAN.md`
- `docs/03_templates/execution/WORK_BLOCK.md`
- `docs/03_templates/execution/STAGE_RESULT.md`
- `docs/03_templates/review/ENGINEERING_REVIEW.md`
- `docs/03_templates/review/VISUAL_REVIEW.md`
- `docs/03_templates/verification/VERIFICATION_REPORT.md`
- `docs/03_templates/release/RELEASE_HANDOFF.md`
- `docs/03_templates/improvement/IMPROVEMENT_RECORD.md`

## Template build strategy

Use one Build Work Block for the initial template layer.

Reasoning:

- The paths already form one coherent registry-defined set.
- Creating them together keeps terminology, section order, metadata fields, and ownership patterns consistent.
- Review and Verification can inspect the complete layer as one unit before profiles depend on it.

## Required constraints for the template build

The template build must not:

- introduce tool-specific process rules;
- introduce profile-specific shortcuts;
- combine artifacts physically;
- add examples or sample project content;
- change existing core files;
- redefine roles, states, approvals, risk tiers, lifecycle stages, or artifact ownership.

## Acceptance criteria

- [x] Template layer is planned from existing `ARTIFACT_REGISTRY.md` paths.
- [x] No actual templates are created in this planning Work Block.
- [x] Profiles, adapters, and examples remain deferred.
- [x] The proposed build scope is bounded and reviewable.
- [x] The next Work Block is clearly defined.

## Risks

- Creating too many template files at once may make Review longer.
- Splitting the first template layer too much may create inconsistent metadata conventions across templates.
- Templates may accidentally drift into examples if they include sample content.

## Mitigations

- Keep templates skeletal and canonical.
- Use placeholders and field descriptions, not project examples.
- Require independent Review and Verification before templates become authoritative.
- Defer profiles until template Review and Verification pass.

## Recommended next Work Block

`WB-013 — Create Initial Template Layer`

Stage: Build

Objective: Create the initial canonical template files listed in `ARTIFACT_REGISTRY.md` under `docs/03_templates/`.

Expected result: Thin, tool-agnostic, profile-neutral Markdown templates for all registry-defined artifact types.

Approved write-set:

- `docs/03_templates/intake/PROJECT_INTAKE.md`
- `docs/03_templates/product/PROJECT_BRIEF.md`
- `docs/03_templates/architecture/SOLUTION_BRIEF.md`
- `docs/03_templates/ux/UX_SPECIFICATION.md`
- `docs/03_templates/design/DESIGN_SPECIFICATION.md`
- `docs/03_templates/design/DESIGN_REVIEW.md`
- `docs/03_templates/implementation/IMPLEMENTATION_PLAN.md`
- `docs/03_templates/execution/WORK_BLOCK.md`
- `docs/03_templates/execution/STAGE_RESULT.md`
- `docs/03_templates/review/ENGINEERING_REVIEW.md`
- `docs/03_templates/review/VISUAL_REVIEW.md`
- `docs/03_templates/verification/VERIFICATION_REPORT.md`
- `docs/03_templates/release/RELEASE_HANDOFF.md`
- `docs/03_templates/improvement/IMPROVEMENT_RECORD.md`
- `docs/plans/WB-013-create-initial-template-layer.md`

Read-only scope:

- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/plans/WB-012-template-layer-planning.md`

Out of scope:

- profiles
- adapters
- examples
- tool-specific rules
- product-specific examples
- changing core governance files
- combining artifacts into profile-specific documents

Risk tier: Tier 1 documentation build

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Verification -> Implementation Planning | Approved template-layer planning | Chat request: `Согласен. Делай` after template layer recommendation | Create planning Work Block |
| 2026-06-24 | Orchestrator | Implementation Planning | Planning complete | `ARTIFACT_REGISTRY.md`, `PROJECT_MAP.md`, `WB-011` | Recommend WB-013 |

## Closeout

- Final status: Complete
- Artifacts created or changed: Template layer planning Work Block
- Files changed:
  - `docs/plans/WB-012-template-layer-planning.md`
- Checks run:
  - read `docs/00_core/ARTIFACT_REGISTRY.md`
  - read `PROJECT_MAP.md`
- Review verdict: not required for this planning note unless Owner requests independent Review
- Verification verdict: not required for this planning note unless Owner requests independent Verification
- Deviations: none
- Residual risks:
  - initial template layer still requires Build, Review, and Verification before it becomes authoritative
  - profiles, adapters, and examples remain deferred
- Required decisions: Owner approval to open `WB-013 — Create Initial Template Layer`
- Next owner/action: open `WB-013 — Create Initial Template Layer` if Owner approves
