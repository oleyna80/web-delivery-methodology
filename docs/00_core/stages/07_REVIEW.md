# Stage: 7 Review

## Purpose

Evaluate a frozen artifact or implementation result against approved inputs, acceptance criteria, scope, quality expectations, and recorded risks without modifying the reviewed result.

## Responsible role

Reviewer.

## Supporting roles

- Orchestrator for routing and verdict recording.
- Domain Specialists when their domain is affected and they did not produce the same result.
- Owner when a finding requires business scope or risk decision.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Build output or subject artifact | In Review | Provides the frozen candidate for review. |
| Stage Result | Submitted | Identifies changed files, evidence, checks, deviations, and risks. |
| Approved governing inputs | Approved | Provide authority for scope and acceptance comparison. |

## Preconditions

- Candidate is frozen for review.
- Reviewer did not produce the same result.
- Acceptance criteria and governing artifacts are available.
- Review scope is clear enough to issue a verdict.

## Allowed activities

- Inspect the candidate against approved inputs, acceptance criteria, quality expectations, and risks.
- Record findings with evidence, severity, and required action.
- Separate blocking findings from recommendations.
- Issue `APPROVE`, `SUPPLEMENT`, or `RECONSIDER`.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Engineering Review or Visual Review | Reviewer | `docs/03_templates/review/ENGINEERING_REVIEW.md` or `docs/03_templates/review/VISUAL_REVIEW.md` when templates exist; otherwise the approved Work Block names the path. |
| Review verdict | Reviewer; Orchestrator records transition | Active Work Block or canonical review report. |

## Output owner

Reviewer owns the review findings and verdict. The Reviewer does not own or edit the reviewed result.

## Acceptance criteria

- Findings cite inspected artifacts or evidence.
- Verdict is one of `APPROVE`, `SUPPLEMENT`, or `RECONSIDER`.
- Blocking and non-blocking findings are separated.
- Required action and routing are clear for each blocking finding.
- Reviewer independence is preserved.

## Checks and evidence

- Scope compliance check against approved write-set and inputs.
- Acceptance criteria review.
- Quality review proportional to risk tier.
- Design or domain review when applicable.

## Approver and gate

Reviewer issues the Review verdict. The Orchestrator records the state transition and routes supplements or reconsideration. Review does not replace Owner approval when Owner authority is required.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Bounded correction needed | Build | Return to `Supplement Required`, then create a bounded fix Work Block. |
| Governing input is wrong | Earliest defective specification stage | Return through `Reconsider Required` and supersede affected artifacts. |
| Reviewer lacks independence | Review | Assign an independent Reviewer. |
| Scope cannot be evaluated | Implementation Planning or responsible specification stage | Clarify acceptance criteria or governing input. |

## Risks

- Reviewer repairs the result instead of reporting findings.
- Recommendations are treated as blocking without rationale.
- Output is approved without checking governing inputs.
- Independence conflicts are missed.

## Stop conditions

- Reviewer contributed to the same result and no independent reviewer is assigned.
- Candidate is not frozen or changes during review.
- Required governing input or acceptance criteria is missing.
- Review discovers higher-tier risk that requires Owner or specialist authority.

## Next allowed stages

- Verification after `APPROVE`.
- Build through a bounded supplement route after `SUPPLEMENT`.
- Earliest defective stage after `RECONSIDER`.
