# Profile: STANDARD_BUSINESS_WEBSITE

## Profile metadata

- Profile ID: `STANDARD_BUSINESS_WEBSITE`
- Profile name: Standard Business Website
- Profile type: standard delivery
- Default risk tier: Tier 1 with escalation to Tier 2 or Tier 3 when triggered
- Primary use: business websites, content sites, service pages, portfolio sections, and moderate content workflows

## Purpose

Provide a standard lifecycle path for business websites and content-oriented delivery where product intent, structure, design, build, review, verification, and handoff should remain clearly separated.

## Intended use

Use this profile when the work includes:

- multiple pages or sections;
- business content structure;
- service descriptions, portfolio sections, or content workflows;
- moderate UX and design decisions;
- reusable components or page patterns;
- content or visual updates that need traceable approval.

Do not use this profile as a shortcut when interactive application behavior, backend logic, data model decisions, account flows, or higher-risk operational concerns dominate the work.

## Default risk tier and escalation

Default: Tier 1.

Escalate to Tier 2 or Tier 3 according to `RISK_TIERING.md` when the work includes architecture contracts, sensitive data, external dependencies, production-readiness changes, difficult rollback, or restricted actions.

## Lifecycle depth by stage

| Stage | Required? | Profile behavior |
| --- | --- | --- |
| 0 Intake | Required | Capture request, audience, constraints, and initial risk signal. |
| 1 Product Definition | Required | Produce an approved Project Brief with goals, scope, success criteria, and non-goals. |
| 2 Solution Architecture | Required when structure, content model, integrations, or operational constraints affect the result | May be lightweight but must record approach and dependencies. |
| 3 UX | Required | Define navigation, content hierarchy, user flows, states, and page structure. |
| 4 UI Design | Required | Define visual direction, page patterns, components, states, and assets. |
| 5 Implementation Planning | Required | Convert approved artifacts into ordered Work Blocks and evidence plan. |
| 6 Build | Required | One Producer or Builder owns writes per Work Block. |
| 7 Review | Required | Independent read-only Review is required. |
| 8 Verification | Required | Independent Verification is required and should cover acceptance criteria and handoff readiness. |
| 9 Release Handoff | Required when outcome is delivered, published, or transferred | Must include owner decision and residual risks. |
| 10 Improvement | Optional but recommended after feedback | Capture validated feedback and follow-up candidates. |

## Required artifacts

- Project Intake.
- Project Brief.
- Solution Brief when architecture, content model, integration, or operational decisions are present.
- UX Specification.
- Design Specification.
- Design Review when visual approval is material.
- Implementation Plan.
- Work Block.
- Stage Result.
- Engineering Review or Visual Review as applicable.
- Verification Report.
- Release Handoff when applicable.
- Improvement Record when feedback becomes new work.

## Optional combined artifacts

Allowed combinations:

- Project Intake may be summarized inside Project Brief only when the original request and routing decision remain identifiable.
- UX Specification and Design Specification may share one physical file only when UX ownership and Design ownership remain explicit.
- Engineering Review and Visual Review may be separate or combined only when both verdict scopes remain identifiable.

## Prohibited omissions

This profile must not omit:

- approved Project Brief;
- explicit scope and non-goals;
- UX direction for user-facing structure;
- visual approval for designed interfaces;
- Implementation Planning before Build;
- Work Block write-set and out-of-scope rules;
- independent Review;
- independent Verification;
- Release Handoff when the result is transferred or published.

## Required reviews and verifications

- Engineering Review: required for implementation outputs that affect structure, behavior, or maintainability.
- Visual Review: required when the output includes visual or UI fidelity decisions.
- Verification: required after Review approval and before handoff.

## Approval gates

- Product Brief approval: Product Owner.
- Architecture approval: Architecture Owner when Solution Brief is required.
- UX approval: Product/UX Owner.
- Design approval: Design Owner and Owner or delegated Design Authority.
- Implementation Plan readiness: Orchestrator or Engineering Owner.
- Review verdict: Reviewer.
- Verification verdict: Verifier.
- Handoff decision: Owner or delegated human authority.

## Specialist review triggers

Require additional specialist review when the work includes:

- architecture or external-contract changes;
- data model or data migration concerns;
- authentication, authorization, security, privacy, regulated, financial, or operationally sensitive behavior;
- external service dependency or runtime configuration;
- non-trivial rollback or recovery planning;
- broad cross-system changes.

## Evidence requirements

Minimum evidence:

- approved Project Brief;
- UX and Design specifications or approved combined artifact;
- architecture evidence when required;
- implementation plan and Work Block write-set;
- changed-file or changed-artifact list;
- Review report with verdict;
- Verification report with evidence;
- handoff decision and residual risk record when applicable.

## Stop conditions

Stop and reassess when:

- a higher-risk trigger appears;
- a required artifact is missing or not approved;
- UX or design decisions conflict with product intent;
- build work depends on unresolved architecture or data decisions;
- Review or Verification cannot be independent;
- handoff readiness cannot be demonstrated.

## Allowed simplifications

- Lightweight Solution Brief when technical complexity is low.
- Combined UX and Design artifact when ownership and approvals remain explicit.
- Focused Verification proportional to risk.

## Profile-specific next-step guidance

Use this profile as the default for non-trivial business websites. Move to `WEB_APPLICATION` when interactive behavior, data, accounts, integrations, or operational concerns become central to the scope.
