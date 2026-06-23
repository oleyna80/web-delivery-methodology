# Stage: 1 Product Definition

## Purpose

Define users, value, scope, constraints, success criteria, and acceptance so that
solution, UX, design, and implementation planning do not proceed from an
ambiguous business request.

## Responsible role

Product Analyst acting as Producer.

## Supporting roles

- Owner for scope and success decisions.
- Orchestrator for routing and Definition of Ready checks.
- Specialist roles when domain, compliance, accessibility, or operational risk is
  visible at product level.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Project Intake | Approved | Establishes accepted problem, requester, and discovery boundary. |

## Preconditions

- Intake is approved by the Owner.
- Business objective and accountable Owner are known.
- Known risk triggers have been recorded.
- Product Definition can be completed without deciding architecture prematurely.

## Allowed activities

- Define users, jobs, value proposition, scope, non-goals, constraints, and
  acceptance boundaries.
- Identify measurable success criteria and priority.
- Record assumptions, dependencies, risks, and open decisions.
- Produce the Project Brief.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Project Brief | Product Owner | `docs/03_templates/product/PROJECT_BRIEF.md` when templates exist; otherwise the approved Work Block names the path. |

## Output owner

Product Owner owns product intent, scope, constraints, success criteria, and
acceptance meaning.

## Acceptance criteria

- Target users and primary needs are identified.
- In-scope and out-of-scope work are explicit.
- Success criteria and acceptance criteria are observable.
- Constraints, assumptions, risks, and unresolved decisions are recorded.
- The Project Brief is usable by Architecture, UX, Design, and Planning.

## Checks and evidence

- Product completeness review against required Project Brief fields.
- Traceability from approved Project Intake to Project Brief.
- Risk tier check against `RISK_TIERING.md`.
- Owner approval evidence.

## Approver and gate

Owner approves product intent, material scope, constraints, and success criteria.
The Orchestrator records the approved status and next allowed transition.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Business problem is wrong or not worth continuing | Intake | Reopen intake or close with rationale. |
| Scope or success criteria are unclear | Product Definition | Revise Project Brief. |
| Architecture decision is needed to define viability | Product Definition | Add explicit open decision and route Architecture only after enough product authority exists. |
| Material risk is discovered | Product Definition | Reclassify risk and obtain required Owner authority. |

## Risks

- Treating implementation ideas as product approval.
- Leaving acceptance criteria subjective.
- Hiding material exclusions or constraints.
- Proceeding to Architecture or UX with unresolved product intent.

## Stop conditions

- Owner cannot approve scope or success criteria.
- Required acceptance criteria cannot be made observable.
- New high or restricted risk appears without authority.
- Product scope expands beyond the approved intake.

## Next allowed stages

- Solution Architecture after Product Brief approval.
- UX only after the architecture inputs required for UX are approved or explicitly
  unnecessary for the profile.
- Intake when the problem, scope, or Owner decision is invalid.
