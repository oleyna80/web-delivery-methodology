# Approval Matrix

## Purpose

This matrix separates recommendation, assurance, workflow routing, and human
authority. A Review verdict confirms quality against a contract. A Verification
verdict confirms reproducible evidence. Neither replaces the Owner decision
required for business scope, accepted risk, or release.

## Approval evidence

Every approval record must identify:

- decision or artifact;
- approved version, candidate, or exact scope;
- approver and delegated authority, if any;
- date and verdict;
- conditions, exceptions, and accepted residual risks;
- next permitted state.

Chat approval is usable only after the Orchestrator records it in the active
Work Block or canonical decision artifact.

## Lifecycle gate matrix

| Lifecycle gate | Producer or proposer | Required assurance | Approval authority | Minimum evidence |
| --- | --- | --- | --- | --- |
| Accept Intake | Product Analyst or Owner | Orchestrator completeness check | Owner | Project Intake and decision rationale |
| Approve Product Definition | Producer / Product Analyst | Product review when non-trivial | Owner | Project Brief, scope, constraints, success criteria |
| Approve Solution Architecture | Architecture Producer | Architecture review; specialist review for affected high-risk domains | Owner or explicitly delegated Architecture Authority; Owner retains risk acceptance | Solution Brief, alternatives, affected contracts, risks |
| Approve UX | UX Producer | UX or product review | Product Owner | UX Specification, flows, states, content needs |
| Approve UI Design | Design Producer | Design review and required accessibility review | Owner or delegated Design Authority | Design Specification, approved reference, review verdict |
| Mark Implementation Plan Ready | Orchestrator or Planning Producer | Contract and dependency review | Orchestrator within approved product scope; Owner for material scope or risk changes | Implementation Plan, dependencies, ordered Work Blocks |
| Start Work Block | Orchestrator | Definition of Ready check | Orchestrator within already approved authority | Ready contract, risk tier, inputs, write-set, checks |
| Accept Build for Review | Producer or Builder | Producer checks | Orchestrator routes only; no business approval implied | Stage Result and check evidence |
| Approve Review gate | Reviewer | Independent read-only review | Reviewer issues verdict; Orchestrator records transition | Review Report and findings disposition |
| Pass Verification gate | Verifier | Independent reproducible checks | Verifier issues verdict; Orchestrator records transition | Verification Report and evidence |
| Approve Release Handoff | Release Producer or Orchestrator | Release-readiness review and passed Verification | Owner or delegated Release Authority | Exact candidate, prerequisites, rollback, monitoring, residual risks |
| Authorize deployment or release | Release Operator proposes execution window | Preflight against approved handoff | Owner or delegated human Release Authority | Authorization tied to candidate and environment |
| Accept Improvement priority | Product Analyst or feedback owner | Product assessment | Owner | Improvement Record, impact, priority rationale |

## Sensitive decision matrix

| Decision or action | Required authority | Additional minimum control |
| --- | --- | --- |
| Expand objective or write-set materially | Owner | Updated Work Block, risk reassessment, affected-artifact review |
| Add or upgrade a dependency | Owner or delegated Engineering Authority | Rationale, compatibility and security review, rollback |
| Change architecture contract | Owner or delegated Architecture Authority | Architecture review and dependency propagation |
| Change database schema or run migration | Owner plus Data/Backend Authority | Migration plan, backup, rollback, verification |
| Change authentication or authorization | Owner plus Security Authority | Threat/security review and negative-path tests |
| Change payments, orders, or financial logic | Owner plus relevant business and engineering authority | Domain review, test evidence, reconciliation and rollback plan |
| Handle secrets or credentials | Named human authority under destination security policy | Least privilege, approved secret channel, no durable plaintext |
| Change production configuration | Owner or delegated Operations Authority | Environment-specific diff, preflight, rollback |
| Deploy or release | Owner or delegated human Release Authority | Passed Verification, exact candidate, rollback and monitoring |
| Destructive operation | Owner and affected-domain authority | Explicit command/action, impact confirmation, backup or recovery plan |
| Commit, push, merge, or publish | Authority defined by destination repository; Owner by default | Reviewed exact diff and target branch or destination |
| Accept high or restricted residual risk | Owner; restricted risk cannot be delegated to an autonomous agent | Written risk, impact, alternatives, conditions, expiry when relevant |

The destination project's stricter rule prevails over this baseline.

## Delegation rules

Delegation must be explicit and recorded with:

- delegating human;
- delegated role or decision type;
- project and scope;
- risk ceiling;
- start and expiry conditions;
- exclusions;
- revocation path.

Delegation does not transfer accountability for restricted risk to an autonomous
agent. An agent may recommend, review, verify, and route; final restricted
authorization remains human.

## Conditional approval

An approval with conditions is not equivalent to completion. Each condition
must have:

- an owner;
- an observable completion criterion;
- a due stage;
- a consequence if unmet.

Conditions that affect safety, core acceptance criteria, or release readiness
block the next gate. Non-blocking recommendations may enter the Improvement
backlog with Owner acknowledgment.

## Approval invalidation

Approval must be reconsidered when:

- the approved artifact or candidate changes materially;
- scope, risk tier, environment, dependency, or external contract changes;
- evidence is found to be incomplete or incorrect;
- the approval conditions expire;
- a downstream failure reveals an upstream defect.

The Orchestrator routes affected artifacts under the State Machine and preserves
the invalidated approval as historical evidence.

