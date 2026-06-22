# Artifact Registry

## Purpose

The Artifact Registry identifies the canonical source of truth passed between
lifecycle stages. It prevents the same decision from being maintained in
several briefs, chats, screenshots, and agent reports without clear authority.

This registry defines artifact types and planned template paths. Project
profiles determine which artifacts are required and whether adjacent artifacts
may share one physical file.

## Artifact statuses

- `Draft` — incomplete and not valid as downstream authority.
- `In Review` — frozen while a reviewer evaluates it.
- `Approved` — valid input for dependent work.
- `Superseded` — retained for history but replaced by a named version.
- `Rejected` — evaluated and intentionally not accepted.

## Canonical artifact types

| Artifact | Producing stage | Semantic owner | Primary consumers | Planned template path |
| --- | --- | --- | --- | --- |
| Project Intake | Intake | Product Owner | Product Definition | `docs/03_templates/intake/PROJECT_INTAKE.md` |
| Project Brief | Product Definition | Product Owner | Architecture, UX, Design, Planning | `docs/03_templates/product/PROJECT_BRIEF.md` |
| Solution Brief | Solution Architecture | Architecture Owner | UX, Planning, frontend/backend Build | `docs/03_templates/architecture/SOLUTION_BRIEF.md` |
| UX Specification | UX | Product/UX Owner | UI Design, Planning, Review | `docs/03_templates/ux/UX_SPECIFICATION.md` |
| Design Specification | UI Design | Design Owner | Planning, Build, visual Review | `docs/03_templates/design/DESIGN_SPECIFICATION.md` |
| Design Review | UI Design gate | Reviewer and Owner approver | Planning and Build | `docs/03_templates/design/DESIGN_REVIEW.md` |
| Implementation Plan | Implementation Planning | Orchestrator/Engineering Owner | Work Blocks and integration | `docs/03_templates/implementation/IMPLEMENTATION_PLAN.md` |
| Work Block | Any execution stage | Orchestrator | Assigned role, Reviewer, Verifier | `docs/03_templates/execution/WORK_BLOCK.md` |
| Stage Result | Any executed stage | Producing role; Orchestrator records receipt | Next gate and downstream role | `docs/03_templates/execution/STAGE_RESULT.md` |
| Engineering Review | Review | Reviewer | Fix routing and Verification | `docs/03_templates/review/ENGINEERING_REVIEW.md` |
| Visual Review | Review | Design Reviewer | Fix routing and Verification | `docs/03_templates/review/VISUAL_REVIEW.md` |
| Verification Report | Verification | Verifier | Release Handoff | `docs/03_templates/verification/VERIFICATION_REPORT.md` |
| Release Handoff | Release Handoff | Release Owner | Owner/release operator | `docs/03_templates/release/RELEASE_HANDOFF.md` |
| Improvement Record | Improvement | Product Owner | New Intake and prioritization | `docs/03_templates/improvement/IMPROVEMENT_RECORD.md` |

The planned template paths above do not yet exist and are not current files.
They become authoritative only after an approved template Work Block creates
them.

## Ownership rules

1. The semantic owner decides the artifact's meaning; the Orchestrator controls
   workflow state and routing.
2. A reviewer supplies a verdict but does not rewrite the reviewed artifact.
3. A verifier supplies evidence and a verdict but does not repair the candidate.
4. Screenshots, prototypes, code, diagrams, test output, and browser recordings
   may be subject artifacts or evidence. The governing specification or report
   must link them by stable path and identify their status.
5. Chat and runtime logs are never the only source of an approved decision.

## Combined artifacts

A profile may combine artifacts in one physical document only when:

- every canonical section remains identifiable;
- semantic ownership and approval are unchanged;
- downstream consumers can locate the required information;
- the profile declares the combined canonical path;
- a change to one section triggers dependency review for the others.

For example, a low-risk landing-page profile may combine Project Intake into
Project Brief and combine UX Specification with Design Specification. A web
application profile will usually split Solution Brief into architecture, data,
API, auth, security, and operational artifacts.

## Dependency rule

When an approved artifact is superseded, all downstream consumers listed in
this registry must be assessed. A dependent artifact remains approved only when
the Orchestrator records why the upstream change does not affect it; otherwise
it returns to `Reconsider Required` under the State Machine.

