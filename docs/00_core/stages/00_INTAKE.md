# Stage: 0 Intake

## Purpose

Turn an initial request, opportunity, or problem signal into a bounded discovery
assignment that the Owner can accept, defer, or decline.

## Responsible role

Product Analyst or Owner acting as Producer.

## Supporting roles

- Orchestrator for completeness and routing.
- Specialist roles only when the request contains obvious domain uncertainty.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Owner request or opportunity | Proposed | Provides the initial business signal and decision context. |

## Preconditions

- The request has an identifiable human Owner or accountable decision source.
- The request can be recorded without exposing secrets or restricted data.
- The Orchestrator can determine whether discovery is worth bounding.

## Allowed activities

- Clarify problem, requester, affected audience, business reason, constraints,
  and urgency.
- Identify obvious exclusions, blockers, and risk triggers.
- Draft a Project Intake artifact or decline rationale.
- Ask for Owner confirmation when the opportunity is ambiguous.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Project Intake | Product Owner | `docs/03_templates/intake/PROJECT_INTAKE.md` when templates exist; otherwise the approved Work Block names the path. |
| Decline or defer decision | Owner | Active Work Block or canonical decision artifact. |

## Output owner

Product Owner owns the business meaning of the accepted intake. The Orchestrator
owns workflow state and routing.

## Acceptance criteria

- [ ] The problem or opportunity is stated in business terms.
- [ ] The Owner or accountable decision source is identified.
- [ ] Initial scope, exclusions, assumptions, and known risks are explicit.
- [ ] The request is either accepted for Product Definition, deferred, or declined
  with rationale.

## Checks and evidence

- Completeness check against the Project Intake fields.
- Owner confirmation or recorded decline/defer decision.
- Risk trigger check against `RISK_TIERING.md`.

## Approver and gate

Owner accepts the intake. The Orchestrator records the transition and confirms
that the next Product Definition Work Block has enough authority to start.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Request is unclear | Intake | Ask for clarification or keep the intake in Draft. |
| No accountable Owner | Intake | Identify decision authority before continuing. |
| Opportunity is not worth defining | Intake | Close as declined with rationale. |
| Restricted information appears | Intake | Pause and route under the required risk controls. |

## Risks

- Treating a casual chat idea as approved scope.
- Missing early restricted-risk triggers.
- Accepting an intake without a real Owner.

## Stop conditions

- No accountable Owner can be identified.
- The request requires handling secrets, credentials, production data, or other
  restricted material without explicit authority.
- The request would require immediate implementation before Product Definition.

## Next allowed stages

- Product Definition when the intake is accepted.
- Improvement when the item is misrouted production feedback already tied to a
  released outcome; redirect it to Improvement rather than continuing Intake.
- Cancelled or deferred state when the Owner declines or postpones the request.
