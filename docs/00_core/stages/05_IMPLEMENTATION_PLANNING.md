# Stage: 5 Implementation Planning

## Purpose

Convert approved product, architecture, UX, and design artifacts into ordered, bounded implementation Work Blocks with explicit dependencies, write-sets, checks, and Definition of Ready.

## Responsible role

Orchestrator or Planning Producer.

## Supporting roles

- Engineering Owner for implementation feasibility.
- Architecture, Frontend, Backend, Data, QA, Security, Accessibility, Content, or Operations Specialists when their domains are affected.
- Owner for material scope or risk changes.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Project Brief | Approved | Defines product scope and success criteria. |
| Solution Brief | Approved | Defines technical approach and constraints. |
| UX Specification | Approved | Defines flows, structure, content needs, and states. |
| Design Specification | Approved | Defines visual direction and implementation reference. |
| Design Review | Approved or resolved | Confirms design is accepted for planning. |

## Preconditions

- Required upstream artifacts are approved or explicitly not required by an approved profile.
- Dependencies, integration points, risk tier, and stop conditions are known enough to bound work.
- Planning can create Work Blocks without expanding product or architecture scope.

## Allowed activities

- Break approved work into ordered Work Blocks.
- Define write-set, read-only scope, acceptance criteria, checks, risks, stop conditions, and assignees for each Work Block.
- Identify integration sequence, review needs, verification needs, and release dependencies.
- Produce the Implementation Plan and ready Work Blocks.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Implementation Plan | Orchestrator / Engineering Owner | `docs/03_templates/implementation/IMPLEMENTATION_PLAN.md` when templates exist; otherwise the approved Work Block names the path. |
| Ready Work Blocks | Orchestrator | `docs/03_templates/execution/WORK_BLOCK.md` when templates exist; otherwise the approved Work Block names the path. |

## Output owner

Orchestrator owns workflow routing and Work Block readiness. Engineering Owner owns implementation feasibility when delegated.

## Acceptance criteria

- [ ] Work Blocks are bounded, ordered, and traceable to approved artifacts.
- [ ] Every Work Block has objective, role, expected result, write-set, read-only scope, out-of-scope, acceptance criteria, checks, risks, stop conditions, and next transition.
- [ ] Dependencies and integration points are explicit.
- [ ] Risk tier and required assurance are recorded.
- [ ] No Work Block relies on unapproved upstream decisions.

## Checks and evidence

- Definition of Ready check for each Work Block.
- Dependency and sequencing review.
- Risk tier and assurance-level check.
- Owner approval evidence for material scope or risk changes.

## Approver and gate

Orchestrator marks the Implementation Plan and Work Blocks ready within approved authority. Owner approval is required for material scope expansion or risk changes.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Missing or conflicting product input | Product Definition | Revise Project Brief. |
| Missing or conflicting architecture input | Solution Architecture | Revise Solution Brief. |
| Missing or conflicting UX input | UX | Revise UX Specification. |
| Missing or conflicting design input | UI Design | Revise Design Specification or review. |
| Work Block cannot be bounded safely | Implementation Planning | Revise plan and stop unsafe execution. |

## Risks

- Hiding scope expansion inside implementation tasks.
- Creating Work Blocks without clear write ownership.
- Omitting integration, review, or verification steps.
- Allowing parallel work before shared contracts are stable.

## Stop conditions

- Required approved input is missing.
- Write-set or ownership is unclear.
- Work requires high or restricted controls not approved by the Owner.
- Acceptance criteria cannot be verified safely.

## Next allowed stages

- Build for ready Work Blocks.
- Product Definition, Solution Architecture, UX, or UI Design when upstream defects are found.
- Review when planning itself is the subject artifact and requires independent assurance.
