# Stage: 6 Build

## Purpose

Produce design assets, frontend, backend, integrations, content, documentation, or other approved deliverables from a ready Work Block and approved source artifacts.

## Responsible role

Builder. `Coder` is a common execution label for this role.

## Supporting roles

- Orchestrator for Work Block routing and state updates.
- Specialists only within explicitly assigned read or write permissions.
- Engineering Owner when the Work Block includes engineering decisions inside approved scope.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Ready Work Block | Ready | Defines objective, role, write-set, acceptance criteria, checks, risks, and stop conditions. |
| Approved source artifacts | Approved | Provide the governing product, architecture, UX, design, content, or implementation authority. |

## Preconditions

- The Work Block satisfies Definition of Ready.
- One writer owns the approved write-set.
- Required inputs and constraints are available.
- The Builder can run or document the required build-level checks.

## Allowed activities

- Create or modify only the approved deliverables in the Work Block write-set.
- Preserve unrelated and pre-existing work.
- Run build-level checks and record evidence.
- Return a Stage Result with changed files, evidence, deviations, residual risks, and recommended next action.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Implementation result | Builder for produced result; semantic owner follows artifact type | Approved Work Block write-set. |
| Stage Result | Producing role; Orchestrator records receipt | `docs/03_templates/execution/STAGE_RESULT.md` when templates exist; otherwise the approved Work Block names the path. |

## Output owner

Builder owns faithful production of the approved result within scope. The Builder does not approve independent Review or Verification of the same result.

## Acceptance criteria

- [ ] Output satisfies the approved Work Block acceptance criteria.
- [ ] Changed files remain inside the approved write-set.
- [ ] Required checks are run or limitations are recorded.
- [ ] Deviations and residual risks are explicit.
- [ ] Stage Result identifies artifacts changed, evidence, and next recommended action.

## Checks and evidence

- Build-level checks named in the Work Block.
- Changed-file report.
- Scope check against approved write-set.
- Evidence for acceptance criteria.

## Approver and gate

The Orchestrator accepts the Stage Result for routing only. Independent Review decides whether the result is approved for Verification.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Build defect within approved scope | Build | Revise through a bounded fix Work Block. |
| Work Block is underspecified | Implementation Planning | Replan and clarify contract. |
| Source artifact is wrong | Earliest defective specification stage | Reconsider and supersede affected artifacts. |
| Higher risk trigger appears | Implementation Planning or relevant authority gate | Pause and reclassify before continuing. |

## Risks

- Expanding the write-set without approval.
- Treating successful build as independent review.
- Modifying sensitive or approval-gated areas without authority.
- Failing to report deviations or residual risks.

## Stop conditions

- Required input is missing, invalid, or contradictory.
- Work requires paths outside approved write-set.
- Restricted-scope work appears without the required approval.
- Required checks cannot be run and no acceptable limitation can be recorded.

## Next allowed stages

- Review after Builder checks pass and Stage Result is returned.
- Implementation Planning when the Work Block is defective.
- Earlier specification stage when the governing artifact is defective.
