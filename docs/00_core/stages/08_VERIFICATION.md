# Stage: 8 Verification

## Purpose

Reproduce the required acceptance checks against the reviewed candidate and record observable evidence before release handoff or completion.

## Responsible role

Verifier.

## Supporting roles

- Orchestrator for state routing and verdict recording.
- QA, Accessibility, Security, Operations, Data, or domain Specialists when required by risk tier and not involved in producing the same result.
- Owner only when verification exposes business risk or release decision needs.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Approved Review Report | Approved or `APPROVE` verdict | Confirms the reviewed candidate is eligible for verification. |
| Candidate result | In Verification | Provides the frozen result to check. |
| Acceptance criteria and required checks | Approved | Defines what must be reproduced and evidenced. |

## Preconditions

- Candidate is frozen for verification.
- Review verdict is `APPROVE` or required supplements are resolved.
- Verifier did not produce the candidate or review the same assurance step.
- Required environment, data, and evidence method are available or limitations are explicit.

## Allowed activities

- Reproduce acceptance checks.
- Record environment, method, evidence, limitations, and residual risks.
- Confirm changed-file or artifact scope when relevant.
- Issue `PASS` or `FAIL`.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Verification Report | Verifier | `docs/03_templates/verification/VERIFICATION_REPORT.md` when templates exist; otherwise the approved Work Block names the path. |
| Verification verdict | Verifier; Orchestrator records transition | Active Work Block or canonical Verification Report. |

## Output owner

Verifier owns verification evidence and verdict. The Verifier does not fix failures or reinterpret missing acceptance criteria as success.

## Acceptance criteria

- Required checks are reproduced or limitations are recorded.
- Evidence is observable and tied to acceptance criteria.
- Verdict is `PASS` or `FAIL`.
- Residual risks and unverified areas are explicit.
- Independence is preserved.

## Checks and evidence

- Acceptance criteria verification.
- Environment and method record.
- Evidence links, logs, screenshots, command outputs, or artifact references when relevant.
- Limitation and residual-risk record.

## Approver and gate

Verifier issues the Verification verdict. The Orchestrator records the transition. Owner approval is still required for release or accepted residual risk when applicable.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Implementation defect only | Build | Create a bounded fix Work Block and repeat Review and Verification. |
| Acceptance criteria or governing input is wrong | Earliest defective specification stage | Reconsider and supersede affected artifacts. |
| Verification cannot be reproduced | Verification or Implementation Planning | Clarify method, environment, or acceptance criteria. |
| Higher-tier risk appears | Responsible authority gate | Pause and obtain required controls before continuing. |

## Risks

- Treating review approval as verification pass.
- Verifying intent instead of observable acceptance criteria.
- Ignoring limitations or environment drift.
- Fixing failures during verification.

## Stop conditions

- Candidate changes during verification.
- Required acceptance criteria are missing or unverifiable.
- Verifier independence is compromised.
- Required environment or evidence path is unavailable and no limitation is acceptable.

## Next allowed stages

- Release Handoff after `PASS` when release or handoff is required.
- Complete after `PASS` for stages without Owner release gate.
- Build or earliest defective specification stage after `FAIL`.
