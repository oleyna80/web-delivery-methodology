# Stage Contract

## Purpose

A Stage Contract defines the reusable rules for a lifecycle stage. It answers
what must be true whenever that stage is used. A Work Block is a concrete
instance of work performed under one Stage Contract.

Profiles may add requirements to a Stage Contract. They may combine artifact
files, but they may not remove safety gates or make required decisions implicit.

## Required fields

Every Stage Contract must define:

| Field | Requirement |
| --- | --- |
| Stage ID and name | Stable identifier from the canonical lifecycle |
| Purpose | Business reason the stage exists |
| Responsible role | Role accountable for producing the result |
| Supporting roles | Optional contributors without canonical write ownership |
| Required inputs | Canonical artifacts and their minimum status |
| Preconditions | Decisions, access, environment, and dependencies required to start |
| Activities | Allowed classes of work |
| Required outputs | Canonical artifact or verifiable result |
| Output owner | Role responsible for semantic accuracy |
| Acceptance criteria | Observable conditions for completion |
| Checks and evidence | How acceptance is demonstrated |
| Approver | Role authorized to pass the gate |
| Failure routes | Destination stage for each class of failure |
| Risks | Stage-specific failure modes |
| Stop conditions | Conditions requiring escalation instead of assumption |
| Next allowed stages | Legal successful transitions |

## Stage Result envelope

Every executed stage or delegated assignment returns a Stage Result to the
Orchestrator. The result may be a section of the active Work Block or a separate
artifact when the approved write-set names its exact path.

Minimum fields:

```text
Work Block ID
Actor and role
Lifecycle stage
Execution state
Outcome or verdict
Artifacts created, changed, or reviewed
Files changed
Evidence and checks
Acceptance criteria status
Deviations from the approved contract
Findings and residual risks
Required decisions
Recommended next action
```

The Stage Result is a handoff envelope. It does not replace the subject artifact
such as the Project Brief, code, design, Review Report, or Verification Report.

## Stage Contract template

```markdown
# Stage: <ID> <Name>

## Purpose

## Responsible role

## Supporting roles

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |

## Preconditions

## Allowed activities

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |

## Acceptance criteria

- [ ]

## Checks and evidence

## Approver and gate

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |

## Risks

## Stop conditions

## Next allowed stages
```

## Contract validation rules

A Stage Contract is invalid when:

- it permits work without an approved input;
- its output has no canonical owner or path;
- success depends on subjective claims without evidence;
- the producing role also grants its own independent Review or Verification;
- it has no route for a failed gate;
- it names a product where a capability or role is sufficient.

