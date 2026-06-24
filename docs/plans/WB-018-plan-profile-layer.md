# Work Block: WB-018 — Plan Profile Layer

## Status

Complete

## Lifecycle stage

Implementation Planning

## Objective

Plan the initial Profile layer under `docs/01_profiles/` after the Template layer passed Verification in WB-017.

## Business reason

Profiles define lifecycle depth for different delivery types. They are the next methodology layer because templates are now verified as profile-neutral and can support profile-specific artifact requirements, combinations, and controls without changing core governance.

## Role

Orchestrator / Documentation Planner

## Profile

Repository maintenance / profile layer planning

## Expected final result

A bounded implementation plan for creating the initial Profile layer without adding adapters, examples, tool-specific behavior, product-specific behavior, or core governance changes.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-017-verify-initial-template-layer.md` | Complete / `PASS` | Template-layer verification gate |
| `PROJECT_MAP.md` | Current main | Planned layer map |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage intent and profile constraints |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Artifact combination constraints |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk-tier controls |
| `docs/00_core/APPROVAL_MATRIX.md` | Current main | Approval gates |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role authority |
| `docs/03_templates/` | Verified | Profile-neutral template foundation |
| Owner approval in chat | Approved | Authority to plan the Profile layer |

## Approved write-set

- `docs/plans/WB-018-plan-profile-layer.md`

## Read-only scope

- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/plans/WB-017-verify-initial-template-layer.md`
- `docs/03_templates/`

## Out of scope

- creating actual profile files
- creating adapters
- creating examples
- editing core governance files
- editing templates
- adding tool-specific rules
- adding vendor-specific assumptions
- adding framework-specific assumptions
- adding product-specific examples
- changing lifecycle architecture, state vocabulary, role authority, approval authority, artifact ownership, or risk tiers

## Current repository facts

- `PROJECT_MAP.md` defines `docs/01_profiles/` as the planned layer for lifecycle depth for different delivery types.
- `LIFECYCLE.md` allows profiles to combine adjacent stages or require additional artifacts, but they must preserve stage intent, approval gates, and failure routes.
- `ARTIFACT_REGISTRY.md` allows a profile to combine artifacts only when canonical sections remain identifiable, semantic ownership and approval are unchanged, downstream consumers can locate the information, the combined path is declared, and dependency review is preserved.
- `RISK_TIERING.md` allows profiles and destination projects to raise a risk tier or add controls, but not to lower the baseline without explicit Owner risk acceptance.
- `WB-017` verified that the template layer is ready for profiles, adapters, and examples.

## Profile layer decision

Create the initial Profile layer as three profile contracts plus an index.

Initial profile set:

1. `LOW_RISK_LANDING_PAGE`
   - Purpose: simplified profile for low-risk marketing, portfolio, or information-only pages.
   - Default risk: Tier 1 unless a higher-tier trigger appears.
   - Expected behavior: may combine adjacent artifacts when ownership and approval evidence remain explicit.

2. `STANDARD_BUSINESS_WEBSITE`
   - Purpose: standard profile for small business websites, content sites, service pages, portfolio sections, and moderate content workflows.
   - Default risk: Tier 1, with escalation to Tier 2 or Tier 3 when risk triggers appear.
   - Expected behavior: keeps core artifacts mostly separate but may allow controlled combinations for content and design where traceability remains clear.

3. `WEB_APPLICATION`
   - Purpose: extended profile for applications with interactive flows, accounts, backend logic, data models, integrations, or operational constraints.
   - Default risk: at least Tier 1 and commonly Tier 2 when architecture, data, auth, security, integration, dependency, infrastructure, or production-readiness triggers appear.
   - Expected behavior: expands artifacts instead of combining them when specialized decisions are needed.

## Why these three profiles

- They map to the lifecycle's simplified and extended delivery concepts without adding product-specific examples.
- They cover the main methodological spread: simple page, standard website, and full web application.
- They give future adapters a stable profile target without naming tools or vendors now.
- They allow examples later to demonstrate one simplified and one extended pipeline.

## Profile contract structure

Each profile should define:

- profile ID and name;
- purpose and intended use;
- default risk tier and escalation rules;
- lifecycle depth by stage;
- required artifacts;
- optional combined artifacts;
- prohibited omissions;
- required reviews and verifications;
- approval gates;
- specialist review triggers;
- evidence requirements;
- stop conditions;
- allowed simplifications;
- profile-specific next-step guidance.

## Proposed profile paths for the first build

- `docs/01_profiles/README.md`
- `docs/01_profiles/LOW_RISK_LANDING_PAGE.md`
- `docs/01_profiles/STANDARD_BUSINESS_WEBSITE.md`
- `docs/01_profiles/WEB_APPLICATION.md`

## Profile build strategy

Use one Build Work Block for the initial profile layer.

Reasoning:

- The three profiles form one coordinated depth model.
- Building them together reduces contradictions in lifecycle depth, artifact combinations, risk escalation, and gate requirements.
- Review can compare simplified, standard, and extended profiles side by side.

## Required constraints for the profile build

The profile build must not:

- remove lifecycle stage intent;
- remove approval gates;
- remove failure routes;
- lower risk-tier controls below `RISK_TIERING.md`;
- make ownership or approval implicit;
- create adapter-specific instructions;
- create examples or filled project artifacts;
- name specific tools, vendors, frameworks, hosting providers, or execution environments;
- edit core governance files or templates.

## Acceptance criteria

- [x] Profile layer is planned after template-layer Verification `PASS`.
- [x] Initial profiles are profile-level contracts, not examples.
- [x] Profile set covers simplified, standard, and extended delivery.
- [x] Profile constraints preserve lifecycle intent, ownership, approval, failure routes, and risk baselines.
- [x] Adapters and examples remain deferred.
- [x] The next Work Block is clearly defined.

## Risks

- Profiles may accidentally become examples if they include project-specific filled content.
- Profiles may weaken core governance if they treat combined artifacts as removed decisions.
- Too many profiles too early may increase maintenance without adding clarity.
- Too few profiles may leave future adapters and examples without useful targets.

## Mitigations

- Keep profiles as contracts, not filled samples.
- Require every simplification to preserve canonical section identity, ownership, approval, and downstream traceability.
- Start with three profile types only.
- Require independent Review and Verification before profiles become authoritative.
- Defer adapters until profiles pass Verification.
- Defer examples until at least one simplified and one extended profile are available.

## Recommended next Work Block

`WB-019 — Create Initial Profile Layer`

Stage: Build

Objective: Create the initial profile index and three profile contracts under `docs/01_profiles/`.

Expected result: Profile layer with simplified, standard, and extended lifecycle-depth profiles.

Approved write-set:

- `docs/01_profiles/README.md`
- `docs/01_profiles/LOW_RISK_LANDING_PAGE.md`
- `docs/01_profiles/STANDARD_BUSINESS_WEBSITE.md`
- `docs/01_profiles/WEB_APPLICATION.md`
- `docs/plans/WB-019-create-initial-profile-layer.md`

Read-only scope:

- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/03_templates/`
- `docs/plans/WB-018-plan-profile-layer.md`

Out of scope:

- adapters
- examples
- tool-specific rules
- vendor-specific assumptions
- framework-specific assumptions
- product-specific examples
- editing core governance files
- editing templates

Risk tier: Tier 1 documentation build

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Verification -> Implementation Planning | Approved WB-018 | Chat request: `начинай WB-018 — Plan Profile Layer` | Create profile planning Work Block |
| 2026-06-24 | Orchestrator | Implementation Planning | Planning complete | `PROJECT_MAP.md`, `LIFECYCLE.md`, `ARTIFACT_REGISTRY.md`, `RISK_TIERING.md`, `WB-017` | Recommend WB-019 |

## Closeout

- Final status: Complete
- Artifacts created or changed: Profile layer planning Work Block
- Files changed:
  - `docs/plans/WB-018-plan-profile-layer.md`
- Checks run:
  - read `PROJECT_MAP.md`
  - read `LIFECYCLE.md`
  - read `ARTIFACT_REGISTRY.md`
  - read `RISK_TIERING.md`
  - reviewed WB-017 readiness result
- Review verdict: not required for this planning note unless Owner requests independent Review
- Verification verdict: not required for this planning note unless Owner requests independent Verification
- Deviations: none
- Residual risks:
  - initial profile layer still requires Build, Review, and Verification before profiles become authoritative
  - adapters and examples remain deferred
- Required decisions: Owner approval to open `WB-019 — Create Initial Profile Layer`
- Next owner/action: open `WB-019 — Create Initial Profile Layer` if Owner approves
