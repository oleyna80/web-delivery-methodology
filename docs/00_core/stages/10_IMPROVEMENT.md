# Stage: 10 Improvement

## Purpose

Capture production feedback, measurements, incidents, learning, and opportunities as governed new work rather than uncontrolled changes to released outcomes.

## Responsible role

Product Analyst or feedback owner acting as Producer.

## Supporting roles

- Owner for priority and scope decisions.
- Orchestrator for routing new intake candidates.
- Operations, QA, Support, Analytics, Security, Accessibility, or domain Specialists when feedback affects their domains.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Released outcome or validated feedback | Complete or Verified | Provides the observed result, incident, opportunity, or measurement that may justify new work. |

## Preconditions

- Feedback, metric, incident, or opportunity is attributable to a released or validated outcome.
- The work can be recorded without bypassing Intake or approval gates.
- Urgent or restricted incidents are routed through the appropriate risk controls.

## Allowed activities

- Capture feedback, metrics, incidents, defects, opportunities, and lessons learned.
- Assess impact, urgency, risk, and candidate priority.
- Produce an Improvement Record.
- Route accepted priorities back to Intake or backlog with rationale.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Improvement Record | Product Owner | `docs/03_templates/improvement/IMPROVEMENT_RECORD.md` when templates exist; otherwise the approved Work Block names the path. |
| Prioritized Intake candidates | Product Owner / Orchestrator | Active Work Block, backlog, or canonical intake path. |

## Output owner

Product Owner owns improvement priority and product meaning. The Orchestrator owns workflow routing into new governed work.

## Acceptance criteria

- [ ] Feedback source, observation, impact, and affected outcome are recorded.
- [ ] Priority, risk, and recommended action are explicit.
- [ ] Accepted items are routed to Intake or backlog as new governed work.
- [ ] Rejected or deferred items include rationale.
- [ ] Incidents or restricted risks are escalated to required authorities.

## Checks and evidence

- Evidence check against feedback, metric, incident record, or stakeholder report.
- Impact and risk assessment.
- Owner priority decision record.
- Routing check for accepted Intake candidates.

## Approver and gate

Owner accepts priorities, defers, rejects, or escalates. The Orchestrator records the next permitted state and opens new Intake only when authorized.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Feedback lacks evidence | Improvement | Clarify source or record as unvalidated. |
| Item is actually unresolved release issue | Release Handoff or Verification | Reopen the responsible stage. |
| Item reveals upstream defect | Earliest defective specification stage | Route through Reconsider Required. |
| Item is accepted for new work | Intake | Create or update Project Intake candidate. |

## Risks

- Treating feedback as authorization to change production directly.
- Mixing backlog wishes with approved scope.
- Failing to escalate incidents or restricted risks.
- Losing rationale for rejected or deferred improvements.

## Stop conditions

- Feedback requires emergency, destructive, production, security, data, legal, or availability action without authority.
- No Owner can prioritize or reject the item.
- The improvement would bypass Intake, Product Definition, or required release controls.

## Next allowed stages

- Intake for accepted improvement candidates.
- Complete when the record is accepted, deferred, or rejected with rationale.
- Responsible earlier stage when the feedback invalidates an approved artifact or released candidate.
