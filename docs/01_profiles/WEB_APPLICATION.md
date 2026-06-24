# Profile: WEB_APPLICATION

## Profile metadata

- Profile ID: `WEB_APPLICATION`
- Profile name: Web Application
- Profile type: extended delivery
- Default risk tier: Tier 1 minimum; commonly Tier 2 when architecture, data, integration, or operational triggers appear
- Primary use: interactive applications with user flows, backend logic, data models, integrations, accounts, or operational constraints

## Purpose

Provide an extended lifecycle path for application delivery where product, architecture, UX, design, implementation planning, build, review, verification, and handoff require stronger separation and evidence.

## Intended use

Use this profile when the work includes one or more of:

- interactive user flows;
- accounts, permissions, or role-based behavior;
- backend business logic;
- data models, data transformations, or persistence decisions;
- external integrations or contracts;
- operational readiness constraints;
- failure paths, recovery paths, or non-trivial quality requirements;
- broad dependencies across lifecycle stages or work streams.

Do not use a simplified profile when these decisions are central to the work.

## Default risk tier and escalation

Default: Tier 1 minimum.

Use Tier 2 controls when the work triggers architecture, data, security, integration, dependency, configuration, production-readiness, difficult rollback, or significant uncertainty conditions from `RISK_TIERING.md`.

Use Tier 3 controls when restricted actions or exact-action human authorization are required by `RISK_TIERING.md` or destination policy.

## Lifecycle depth by stage

| Stage | Required? | Profile behavior |
| --- | --- | --- |
| 0 Intake | Required | Capture business request, affected users, constraints, and initial risk signals. |
| 1 Product Definition | Required | Produce an approved Project Brief with users, scope, non-goals, success criteria, and constraints. |
| 2 Solution Architecture | Required | Produce a Solution Brief and split specialized artifacts when needed. |
| 3 UX | Required | Define flows, states, information structure, edge cases, and interaction behavior. |
| 4 UI Design | Required for user-facing work | Define visual system, screens, components, states, and design handoff evidence. |
| 5 Implementation Planning | Required | Define Work Blocks, integration plan, dependencies, gates, checks, and risk controls. |
| 6 Build | Required | One Producer or Builder owns each Work Block write-set. Parallel work requires explicit interfaces and integration plan. |
| 7 Review | Required | Independent read-only Review is required, with specialist review for triggered domains. |
| 8 Verification | Required | Independent Verification must reproduce acceptance checks and cover integration evidence. |
| 9 Release Handoff | Required for transfer, publication, or operational handoff | Must include prerequisites, recovery, monitoring, support, owner decision, and residual risks. |
| 10 Improvement | Recommended | Capture feedback, incidents, measurements, and follow-up candidates. |

## Required artifacts

- Project Intake.
- Project Brief.
- Solution Brief.
- Specialized architecture artifacts when needed, such as data model, integration contract, operational plan, quality strategy, or risk-specific analysis.
- UX Specification.
- Design Specification and Design Review when user-facing design exists.
- Implementation Plan.
- Work Blocks.
- Stage Results.
- Engineering Review.
- Visual Review when relevant.
- Verification Report.
- Release Handoff.
- Improvement Record when feedback or follow-up work appears.

## Optional combined artifacts

This profile normally keeps artifacts separate.

Allowed combinations are limited to low-complexity adjacent sections where:

- every canonical section remains identifiable;
- semantic owner and approval remain explicit;
- downstream consumers can locate the required information;
- risk tier remains unchanged or is raised;
- dependency review is preserved.

## Prohibited omissions

This profile must not omit:

- Solution Architecture for application behavior;
- explicit data, integration, or operational decisions when they affect the outcome;
- Implementation Planning before Build;
- Work Block write-set and stop conditions;
- specialist review for triggered domains;
- independent Review;
- independent Verification;
- Release Handoff for delivered outcomes;
- residual risk recording.

## Required reviews and verifications

- Engineering Review: required for implementation outputs.
- Visual Review: required for user-facing UI outputs.
- Specialist Review: required for triggered architecture, data, integration, security, privacy, operational, or regulated domains.
- Verification: required after Review approval and before handoff.
- Preflight Verification: required when restricted or high-impact handoff controls are triggered.

## Approval gates

- Product Brief approval: Product Owner.
- Solution Architecture approval: Architecture Owner and risk owners as applicable.
- UX approval: Product/UX Owner.
- Design approval: Design Owner and Owner or delegated Design Authority.
- Implementation Plan readiness: Orchestrator or Engineering Owner.
- Specialist review approvals: domain reviewers when triggered.
- Review verdict: Reviewer.
- Verification verdict: Verifier.
- Handoff decision: Owner or delegated human authority.

## Specialist review triggers

Require specialist review when work includes:

- architecture or external-contract changes;
- data model, migration, transformation, or data-retention decisions;
- authentication, authorization, permission, abuse-control, privacy, or security-control decisions;
- regulated, financial, order, inventory, or business-critical behavior;
- external service dependency or runtime configuration;
- infrastructure, deployment, or production-readiness changes;
- difficult rollback, recovery, or incident response considerations;
- significant uncertainty with downstream cost.

## Evidence requirements

Minimum evidence:

- approved Project Brief;
- approved Solution Brief and specialized artifacts when required;
- approved UX Specification;
- approved Design Specification when applicable;
- Implementation Plan with dependencies, Work Blocks, risk controls, and checks;
- Stage Results for executed Work Blocks;
- Review reports with findings and verdicts;
- Verification Report with evidence and limitations;
- Handoff readiness evidence;
- residual risks and owner decisions.

## Stop conditions

Stop and reassess when:

- a higher risk tier appears;
- a required specialist decision is missing;
- architecture, data, UX, design, or implementation artifacts conflict;
- integration boundaries are unclear;
- acceptance criteria cannot be verified safely;
- rollback or recovery is missing where required;
- Review or Verification cannot remain independent;
- authority for a high-risk or restricted action is unclear.

## Allowed simplifications

- None that remove required stage intent, approval, evidence, Review, Verification, or risk controls.
- Documentation may be concise when evidence is clear, but required decisions must remain explicit.

## Profile-specific next-step guidance

Use this profile when the work behaves like an application rather than a presentation site. If risk triggers become material, raise the risk tier and add required specialist review before Build continues.
