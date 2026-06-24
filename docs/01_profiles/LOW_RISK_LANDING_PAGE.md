# Profile: LOW_RISK_LANDING_PAGE

## Profile metadata

- Profile ID: `LOW_RISK_LANDING_PAGE`
- Profile name: Low-Risk Landing Page
- Profile type: simplified delivery
- Default risk tier: Tier 1 unless a higher-tier trigger appears
- Primary use: low-risk marketing, portfolio, campaign, or information-only pages

## Purpose

Provide a simplified lifecycle path for low-risk pages while preserving the canonical decisions, ownership, approval evidence, Review, and Verification required by the core methodology.

## Intended use

Use this profile when the work is primarily:

- static or low-risk content presentation;
- visual layout and copy assembly;
- a small number of pages or sections;
- reversible and low impact;
- free of higher-tier triggers.

Do not use this profile when the work includes data mutation, account flows, sensitive information handling, business-critical automation, external-contract changes, or other Tier 2 or Tier 3 triggers.

## Default risk tier and escalation

Default: Tier 1.

Escalate when any `RISK_TIERING.md` Tier 2 or Tier 3 trigger appears. Escalation may require using `STANDARD_BUSINESS_WEBSITE` or `WEB_APPLICATION`, depending on the affected decisions.

## Lifecycle depth by stage

| Stage | Required? | Profile behavior |
| --- | --- | --- |
| 0 Intake | Required | May be brief but must identify request, scope signal, and constraints. |
| 1 Product Definition | Required | May combine Project Intake and Project Brief when both sections remain identifiable. |
| 2 Solution Architecture | Conditional | Required when technical approach, integrations, data, or operational constraints affect the result. |
| 3 UX | Required | May be lightweight; must describe page structure, user path, required states, and content hierarchy. |
| 4 UI Design | Required | May combine UX Specification and Design Specification when interaction and visual decisions remain identifiable. |
| 5 Implementation Planning | Required | May be compact; must still define Work Blocks, write-set, checks, and gate sequence. |
| 6 Build | Required | One Producer or Builder owns writes. |
| 7 Review | Required | Independent read-only Review is required. |
| 8 Verification | Required | Independent Verification is required, proportional to risk. |
| 9 Release Handoff | Required when outcome is handed off or published | Must record owner decision and residual risks. |
| 10 Improvement | Optional | Used when feedback or follow-up candidates are captured. |

## Required artifacts

- Project Brief, optionally containing Project Intake as a named section.
- UX Specification and Design Specification, optionally combined when sections and approvals remain clear.
- Implementation Plan or compact planning section.
- Work Block.
- Stage Result.
- Review Report.
- Verification Report.
- Release Handoff when applicable.

## Optional combined artifacts

Allowed combinations:

- Project Intake inside Project Brief.
- UX Specification and Design Specification in one file.
- Implementation Plan and Work Block in one file only when the work remains bounded and traceable.

Every combined artifact must preserve canonical section names, semantic owners, approval evidence, and downstream traceability.

## Prohibited omissions

This profile must not omit:

- Product Owner approval of intent and scope;
- visual approval when UI is produced;
- explicit write-set;
- independent Review;
- independent Verification;
- residual risk recording;
- handoff decision when the result leaves the build context.

## Required reviews and verifications

- Review: required for all non-trivial output.
- Visual Review: required when visual design or implemented UI is part of the deliverable.
- Verification: required after Review approval.

## Approval gates

- Product intent and scope: Product Owner.
- Architecture approval: Architecture Owner when Solution Architecture is required.
- Visual approval: Owner or delegated Design Authority.
- Review verdict: Reviewer.
- Verification verdict: Verifier.
- Handoff or release decision: Owner or delegated human authority.

## Specialist review triggers

Require a fuller profile or specialist review when work unexpectedly includes:

- architecture or external-contract decisions;
- data model or data handling changes;
- authentication, authorization, or security-control decisions;
- regulated, financial, or operationally sensitive behavior;
- deployment or production-readiness controls;
- difficult rollback or recovery.

## Evidence requirements

Minimum evidence:

- approved scope statement;
- approved visual reference or design decision;
- changed-file or changed-artifact list;
- review findings and verdict;
- verification evidence and verdict;
- residual risks and handoff decision when applicable.

## Stop conditions

Stop and reassess when:

- the work is no longer information-only or low impact;
- a Tier 2 or Tier 3 trigger appears;
- required approval is missing;
- Review or Verification cannot be independent;
- a combined artifact hides ownership or approval evidence.

## Allowed simplifications

- Fewer physical artifact files.
- Shorter briefs and specifications.
- Combined adjacent artifacts when traceability is preserved.
- Focused Verification proportional to risk.

## Profile-specific next-step guidance

If work remains simple and low risk, proceed through the simplified profile. If scope expands beyond low-risk presentation work, route to `STANDARD_BUSINESS_WEBSITE` or `WEB_APPLICATION` before Build continues.
