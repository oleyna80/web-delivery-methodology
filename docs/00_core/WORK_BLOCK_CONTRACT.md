# Work Block Contract

## Purpose

A Work Block is the bounded execution contract for one non-trivial assignment.
It instantiates one lifecycle stage, one profile, one objective, and one approved
write-set. It is also the canonical task audit trail.

The Orchestrator is the only writer of Work Block status, execution-log entries,
review verdicts, acceptance status, and closeout. Builders, reviewers, verifiers,
and specialist agents return structured Stage Results to the Orchestrator.

## Bootstrap rule

Until the canonical Work Block template exists, repository-maintenance Work
Blocks may be created in `docs/plans/` using the inline canonical template in
this document. This bootstrap path is limited to maintaining this methodology
repository and does not make planned template paths authoritative.

## Required contract

Every non-trivial Work Block records:

- identifier and title;
- status and lifecycle stage;
- objective and business reason;
- assigned role and selected profile;
- expected final result;
- authoritative input artifacts;
- approved write-set or explicitly read-only scope;
- out-of-scope paths and decisions;
- deliverables and acceptance criteria;
- risks and stop conditions;
- checks and required evidence;
- approver and next allowed transition.

## Write ownership

- One Coder owns all writes during a Build step.
- The Coder does not edit the active Work Block.
- Reviewers and Verifiers are read-only.
- A finding that requires changes creates a routed Coder/Fix step.
- Scope expansion requires Owner approval before the new path is written.
- Commit, push, deploy, destructive operations, secrets, dependencies,
  configuration, databases, auth, payments, or production changes require the
  approval gates applicable to the destination project.

## Canonical template

```markdown
# Work Block: <ID> — <Title>

## Status

Proposed | Draft | Ready | In Progress | In Review | Supplement Required |
Reconsider Required | In Verification | Verified | Awaiting Owner Decision |
Complete | Blocked | Superseded | Cancelled

## Lifecycle stage

## Objective

## Business reason

## Role

## Profile

## Expected final result

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |

## Approved write-set

## Read-only scope

## Out of scope

## Deliverables

## Acceptance criteria

- [ ]

## Risks

## Checks and evidence

## Stop conditions

## Plan

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |

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
```

## Small Task Path

A trivial, reversible, single-purpose change may use a compact inline contract:

```text
objective
role
allowed file
expected result
check
outcome
```

The Small Task Path does not bypass repository safety, secrets handling,
approval-sensitive areas, or changed-file reporting. If independent Review,
multiple writers, architectural judgment, or more than one domain is involved,
use a full Work Block.

## Closeout rule

A Work Block is complete only when its output exists, checks are recorded,
required verdicts have passed, deviations and residual risks are explicit, and
the next owner or action is named.
