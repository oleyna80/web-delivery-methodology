# Work Block: WB-013 — Create Initial Template Layer

## Status

In Progress

## Lifecycle stage

Build

## Objective

Create the initial canonical template files listed in `ARTIFACT_REGISTRY.md` under `docs/03_templates/`.

## Business reason

The template layer provides stable, profile-neutral artifact structures needed before profiles, adapters, and examples can depend on canonical document formats.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / template layer build

## Expected final result

Thin, tool-agnostic, profile-neutral Markdown templates for all registry-defined artifact types.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-012-template-layer-planning.md` | Complete | Planning authority |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Artifact list and planned paths |
| `docs/00_core/STAGE_CONTRACT.md` | Current main | Stage structure authority |
| `docs/00_core/WORK_BLOCK_CONTRACT.md` | Current main | Work Block authority |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role authority |
| `docs/00_core/APPROVAL_MATRIX.md` | Current main | Approval authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk authority |
| Owner approval in chat | Approved | Authority to execute WB-013 |

## Approved write-set

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

## Read-only scope

- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/plans/WB-012-template-layer-planning.md`

## Out of scope

- creating profiles
- creating adapters
- creating examples
- adding tool-specific rules
- adding product-specific examples
- changing core governance files
- combining artifacts into profile-specific documents

## Deliverables

- Initial template files for each registry-defined artifact type.
- Work Block closeout with changed-file scope and residual risks.

## Acceptance criteria

- [ ] All planned template paths from `ARTIFACT_REGISTRY.md` are created.
- [ ] Templates are thin Markdown skeletons, not product examples.
- [ ] Templates preserve canonical ownership and status semantics.
- [ ] Templates include inputs and authority sections where relevant.
- [ ] Templates include evidence, decision, acceptance, review, or verification sections where relevant.
- [ ] No profile-, adapter-, example-, tool-, vendor-, framework-, deployment-, product-, or application-specific behavior is added.
- [ ] Core governance files are not modified.
- [ ] Changed files remain inside the approved write-set.

## Risks

- Templates may become too detailed and accidentally act as examples.
- Templates may become too vague and fail to guide future Work Blocks.
- Metadata may become inconsistent across artifact types.

## Checks and evidence

- Direct read of created template paths.
- Compare changed files against approved write-set.
- Search for tool-, vendor-, framework-, deployment-, product-, or application-specific leakage if useful.

## Stop conditions

- Build requires changing core governance files.
- Build requires profile, adapter, or example decisions.
- Build requires product-specific or tool-specific content.

## Plan

1. Create template directories and files listed in `ARTIFACT_REGISTRY.md`.
2. Keep every template profile-neutral and tool-agnostic.
3. Run changed-file scope checks.
4. Close this Work Block and route to independent Review.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Planning -> Build | Approved WB-013 | Chat request: `Запускай WB-013 — Create Initial Template Layer` | Create initial template layer |
| 2026-06-24 | Orchestrator | Build | Work Block opened | `docs/plans/WB-013-create-initial-template-layer.md` | Create templates |

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
