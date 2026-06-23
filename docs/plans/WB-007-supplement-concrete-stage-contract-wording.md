# Work Block: WB-007 — Supplement Concrete Stage Contract Wording

## Status

In Progress

## Lifecycle stage

Build

## Objective

Apply bounded wording and formatting supplements for non-blocking WB-005 findings F-001 through F-004 after WB-006 Verification returned `PASS`.

## Business reason

The concrete Stage Contracts are verified, but small wording and formatting findings should be resolved before profiles, adapters, templates, or examples depend on the stage-contract vocabulary.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / core documentation supplement

## Expected final result

WB-005 non-blocking findings F-001 through F-004 are resolved without changing lifecycle architecture, state vocabulary, role authority, approval authority, artifact ownership, risk tiers, or adding profile/tool/vendor-specific behavior.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-005-review-concrete-stage-contracts.md` | Complete / `APPROVE` | Review findings source |
| `docs/plans/WB-006-verify-concrete-stage-contracts.md` | Complete / `PASS` | Verification source |
| `docs/00_core/STAGE_CONTRACT.md` | Current main | Acceptance-criteria format authority |
| `docs/00_core/STATE_MACHINE.md` | Current main | State and verdict vocabulary authority |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Artifact ownership authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Lifecycle routing authority |
| Owner approval in chat | Approved | Authority to execute this bounded supplement |

## Approved write-set

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
- `docs/plans/WB-007-supplement-concrete-stage-contract-wording.md`

## Read-only scope

- `docs/00_core/STAGE_INDEX.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STATE_MACHINE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/plans/WB-005-review-concrete-stage-contracts.md`
- `docs/plans/WB-006-verify-concrete-stage-contracts.md`

## Out of scope

- editing existing core governance files outside `docs/00_core/stages/`
- editing `STAGE_INDEX.md`
- creating profiles
- creating adapters
- creating templates
- creating examples
- adding tool-specific or product-specific behavior
- changing lifecycle architecture, state vocabulary, role authority, approval authority, artifact ownership, or risk tiers
- adding application code, dependencies, secrets, deployment automation, or provider configuration

## Deliverables

- F-001: acceptance criteria in all 11 stage files use checkbox bullets.
- F-002: non-canonical required-status wording is replaced or clarified in affected stage files.
- F-003: UI Design Output owner section restates Design Review ownership.
- F-004: Intake next-stage routing clarifies redirected production feedback.
- Work Block closeout with checks and residual risks.

## Acceptance criteria

- [ ] All 11 stage files use `- [ ]` bullets in the Acceptance criteria section.
- [ ] `07_REVIEW.md`, `09_RELEASE_HANDOFF.md`, and `10_IMPROVEMENT.md` no longer use `Submitted`, `Passed`, or `Current` as required-status terms in Required inputs tables.
- [ ] `04_UI_DESIGN.md` Output owner section explicitly names Design Review ownership by Reviewer and Owner approver.
- [ ] `00_INTAKE.md` clarifies that production feedback is redirected to Improvement rather than treated as a normal forward Intake transition.
- [ ] Changed files remain inside the approved write-set.
- [ ] No profile-, adapter-, tool-, vendor-, framework-, provider-, deployment-, or application-specific behavior is added.

## Risks

- Formatting edits across all stage files may introduce accidental content drift.
- Replacing non-canonical status wording may still need later review for mechanical gate interpretation.

## Checks and evidence

- Direct read of affected sections after edits.
- Search for unresolved `Submitted`, `Passed`, and `Current` terms in stage files.
- Search for vendor/tool leakage terms.
- Compare changed files against approved write-set.

## Stop conditions

- A fix requires changing existing core governance files outside the approved write-set.
- A fix requires changing lifecycle architecture or authority boundaries.
- A fix requires profile, adapter, template, example, tool, vendor, or implementation-specific content.

## Plan

1. Apply checkbox formatting to Acceptance criteria sections in all 11 stage files.
2. Resolve F-002 wording in `07_REVIEW.md`, `09_RELEASE_HANDOFF.md`, and `10_IMPROVEMENT.md`.
3. Resolve F-003 wording in `04_UI_DESIGN.md`.
4. Resolve F-004 wording in `00_INTAKE.md`.
5. Run checks and close this Work Block.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-23 | Owner | Verification -> Build | Approved WB-007 | Chat request: `WB-007 — Supplement Concrete Stage Contract Wording` | Execute bounded supplement |
| 2026-06-23 | Orchestrator | Build | Work Block opened | `docs/plans/WB-007-supplement-concrete-stage-contract-wording.md` | Apply F-001 through F-004 |

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
