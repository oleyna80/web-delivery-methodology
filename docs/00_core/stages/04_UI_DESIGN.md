# Stage: 4 UI Design

## Purpose

Define visual direction, design system, responsive behavior, assets, and approved interface reference before implementation planning and build depend on visual decisions.

## Responsible role

Design Producer or Design Analyst acting as Producer.

## Supporting roles

- Owner or delegated Design Authority for visual approval.
- Product/UX Owner for interaction and structure consistency.
- Accessibility, Frontend, Content, or Brand Specialists when relevant.
- Orchestrator for routing and readiness checks.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| UX Specification | Approved | Defines structure, flows, content needs, and states that visual design must support. |

## Preconditions

- UX direction and coverage are approved.
- Brand, asset, accessibility, and responsive requirements are known or recorded as open decisions.
- Visual work can proceed without changing UX structure.

## Allowed activities

- Define visual direction, layout system, typography, color, components, responsive behavior, and asset requirements.
- Produce approved interface references, mockups, or design notes.
- Identify accessibility and implementation constraints.
- Produce Design Specification and Design Review decision evidence.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Design Specification | Design Owner | `docs/03_templates/design/DESIGN_SPECIFICATION.md` when templates exist; otherwise the approved Work Block names the path. |
| Design Review | Reviewer and Owner approver | `docs/03_templates/design/DESIGN_REVIEW.md` when templates exist; otherwise the approved Work Block names the path. |

## Output owner

Design Owner owns the visual direction and design-system meaning. Reviewer and Owner approver own the Design Review decision evidence. Owner or delegated Design Authority owns visual approval.

## Acceptance criteria

- [ ] Visual direction and interface reference are explicit.
- [ ] Design decisions trace to approved UX and product constraints.
- [ ] Responsive behavior and asset requirements are recorded.
- [ ] Accessibility constraints and visual risks are identified.
- [ ] Owner or delegated Design Authority grants visual approval or records required revision.

## Checks and evidence

- Design review against UX Specification.
- Accessibility review proportional to risk and interface scope.
- Responsive coverage check.
- Owner or delegated Design Authority approval evidence.

## Approver and gate

Owner or delegated Design Authority grants visual approval. The Orchestrator records the decision and routes defects to UI Design or UX when structure is wrong.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Visual direction is not approved | UI Design | Revise Design Specification. |
| Design conflicts with UX structure | UX | Reopen UX and supersede affected design work. |
| Accessibility concern blocks approval | UI Design | Revise design and obtain required review. |
| Implementation constraint invalidates design | Solution Architecture or UX | Reconsider affected upstream artifact. |

## Risks

- Treating visual approval as UX approval.
- Omitting responsive or accessibility requirements.
- Approving assets without stable source paths or usage rights.
- Designing components that cannot be implemented within architecture constraints.

## Stop conditions

- Approved UX is missing or unstable.
- Visual approval authority is not identified.
- Design requires changing product, architecture, or UX scope.
- Required assets, brand rules, or accessibility constraints are unavailable and blocking.

## Next allowed stages

- Implementation Planning after approved product, architecture, UX, and design artifacts exist.
- UX when structure or interaction defects are discovered.
- UI Design revision when visual defects are bounded to design.
