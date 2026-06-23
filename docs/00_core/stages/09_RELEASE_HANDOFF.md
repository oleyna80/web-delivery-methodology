# Stage: 9 Release Handoff

## Purpose

Present a release-ready package, operational prerequisites, rollback information, monitoring path, unresolved risks, and required human decision for release or handoff.

## Responsible role

Release Producer or Orchestrator.

## Supporting roles

- Release Operator for execution readiness.
- Operations, Security, QA, Data, Backend, Frontend, or domain Specialists when their controls are relevant.
- Owner or delegated human Release Authority for release or acceptance decision.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Verification Report | `PASS` verdict recorded | Confirms the candidate passed required checks. |
| Candidate result | Verified | Identifies the exact artifact, build, package, documentation, or deliverable eligible for handoff. |
| Residual risk record | Approved or explicitly recorded | Identifies known unresolved conditions and decision needs. |

## Preconditions

- Verification verdict is `PASS`.
- Exact candidate and target environment or destination are identified.
- Prerequisites, rollback or recovery path, and monitoring or support path are known.
- Owner or delegated Release Authority is identified.

## Allowed activities

- Assemble release or handoff summary.
- Record candidate identity, prerequisites, deployment or publication needs, rollback, monitoring, and support expectations.
- Record residual risks, limitations, and required decisions.
- Present the package for human release authorization or accepted handoff.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Release Handoff | Release Owner | `docs/03_templates/release/RELEASE_HANDOFF.md` when templates exist; otherwise the approved Work Block names the path. |
| Owner decision | Owner or delegated Release Authority | Active Work Block or canonical Release Handoff. |

## Output owner

Release Owner owns release-readiness presentation. Owner or delegated human Release Authority owns release authorization and risk acceptance.

## Acceptance criteria

- [ ] Exact candidate is identified.
- [ ] Verification evidence is referenced.
- [ ] Prerequisites, rollback or recovery, monitoring, and support path are explicit.
- [ ] Residual risks and unresolved decisions are recorded.
- [ ] Owner or delegated human Release Authority authorizes release, accepts handoff, holds, or routes required changes.

## Checks and evidence

- Release readiness review against passed Verification Report.
- Candidate identity check.
- Preflight, rollback, monitoring, and support checklist proportional to risk tier.
- Owner or delegated Release Authority decision record.

## Approver and gate

Owner or explicitly delegated human Release Authority authorizes release, accepts handoff, or places the candidate on hold. Agents may recommend and prepare evidence but do not own restricted release authority.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Release prerequisites missing | Release Handoff | Complete prerequisites or record hold decision. |
| Verification evidence insufficient | Verification | Reverify candidate. |
| Candidate changed after verification | Review or Verification | Repeat required assurance. |
| Owner rejects risk or scope | Build or responsible specification stage | Revise candidate or governing artifact. |

## Risks

- Treating `PASS` verification as release authorization.
- Handoff omits rollback, monitoring, or support expectations.
- Candidate identity drifts after verification.
- Residual risk is accepted without human authority.

## Stop conditions

- Exact candidate cannot be identified.
- Verification is missing, failed, or stale.
- Release would require unapproved production, destructive, credential, financial, legal, or availability risk.
- Required human authority is unavailable.

## Next allowed stages

- Complete after Owner accepts handoff or authorizes release as applicable.
- Build, Review, Verification, or responsible specification stage when release readiness fails.
- Improvement after released outcome or validated feedback exists.
