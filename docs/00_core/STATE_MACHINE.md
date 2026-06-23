# Delivery State Machine

## Purpose

Lifecycle stages describe what kind of work is occurring. Execution states
describe the status of one artifact, Work Block, or release candidate. Keeping
these concepts separate prevents a document labelled "Design" from being
mistaken for an approved design.

## Canonical states

| State | Meaning | Who may enter it |
| --- | --- | --- |
| Proposed | Requested but not yet accepted into delivery | Owner or Orchestrator |
| Draft | Being specified; not ready for execution or downstream reliance | Assigned author |
| Ready | Inputs and contract satisfy Definition of Ready | Orchestrator |
| In Progress | One approved writer is producing the result | Orchestrator starts; assigned writer executes |
| In Review | Result is frozen for read-only review | Orchestrator |
| Supplement Required | Bounded corrections are required without invalidating the governing specification | Reviewer through verdict; Orchestrator records transition |
| Reconsider Required | A requirement, architecture, UX, design, or plan decision must be reopened | Reviewer or Verifier through verdict; Orchestrator routes transition |
| In Verification | Reviewed candidate is frozen for reproducible checks | Orchestrator |
| Verified | Verification passed; candidate is eligible for the next gate | Verifier through verdict; Orchestrator records transition |
| Awaiting Owner Decision | Human approval, release authorization, or scope decision is required | Orchestrator |
| Complete | Contract is fulfilled and closeout is recorded | Orchestrator after required approvals |
| Blocked | Work cannot progress without a named decision or external condition | Orchestrator |
| Superseded | A newer canonical artifact replaces this version | Artifact owner or Orchestrator |
| Cancelled | Owner intentionally terminates the work | Owner |

## Normal transition

```text
Proposed
  -> Draft
  -> Ready
  -> In Progress
  -> In Review
  -> In Verification
  -> Verified
  -> Awaiting Owner Decision     # when the stage requires human approval
  -> Complete
```

Stages without an Owner gate may transition from `Verified` directly to
`Complete`. Documentation-only specification stages may use evidence-based
review as their verification, but the Reviewer and Verifier responsibilities
must remain separately recorded.

## Review verdicts

- `APPROVE`: transition from `In Review` to `In Verification`.
- `SUPPLEMENT`: transition to `Supplement Required`, then to `In Progress` for
  the same bounded scope. After correction, repeat Review.
- `RECONSIDER`: transition to `Reconsider Required`. The Orchestrator identifies
  the earliest invalid stage, supersedes affected downstream artifacts, and
  opens a new Work Block there.

Reviewer verdicts do not directly modify the reviewed artifact.

## Verification verdicts

- `PASS`: transition from `In Verification` to `Verified`.
- `FAIL`: transition to `Reconsider Required` when a governing decision is
  invalid, or back to `In Progress` through a new fix Work Block when the defect
  is confined to implementation.

Verifier findings do not directly fix the candidate.

## Blocking and resumption

Any non-terminal state may enter `Blocked`. The audit entry must name:

- the blocking condition;
- the responsible decision owner;
- affected artifacts;
- the state to resume when unblocked.

Removing the condition does not silently resume work. The Orchestrator records
the resumption and rechecks Definition of Ready.

## Change propagation

When an approved upstream artifact changes:

1. mark the replaced version `Superseded`;
2. identify all dependent artifacts using the Artifact Registry;
3. move affected work to `Reconsider Required`;
4. decide which artifacts require revision, review, and reverification;
5. preserve prior decisions and evidence rather than rewriting history.

## Forbidden transitions

- `Draft -> In Progress` without `Ready`.
- `In Progress -> Complete` without required Review and Verification.
- `In Review -> In Progress` without a recorded verdict and routed fix scope.
- `In Verification -> Complete` without `PASS`.
- `Verified -> Complete` for a release-governed stage without the required Owner decision.
- Any transition based only on chat history or an unrecorded verbal assumption.
