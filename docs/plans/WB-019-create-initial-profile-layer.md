# Work Block: WB-019 — Create Initial Profile Layer

## Status

In Progress

## Lifecycle stage

Build

## Objective

Create the initial profile index and three profile contracts under `docs/01_profiles/`.

## Business reason

WB-018 planned the Profile layer after the Template layer passed Verification in WB-017. Profiles now provide delivery-depth contracts for simplified, standard, and extended methodology use without changing core governance.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / profile layer build

## Expected final result

Profile layer with simplified, standard, and extended lifecycle-depth profiles.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-018-plan-profile-layer.md` | Complete | Profile layer planning authority |
| `docs/plans/WB-017-verify-initial-template-layer.md` | Complete / `PASS` | Template-layer verification gate |
| `PROJECT_MAP.md` | Current main | Planned layer map |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage intent and profile constraints |
| `docs/00_core/ARTIFACT_REGISTRY.md` | Current main | Artifact combination constraints |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk-tier controls |
| `docs/00_core/APPROVAL_MATRIX.md` | Current main | Approval gates |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role authority |
| `docs/03_templates/` | Verified | Profile-neutral template foundation |
| Owner approval in chat | Approved | Authority to execute WB-019 |

## Approved write-set

- `docs/01_profiles/README.md`
- `docs/01_profiles/LOW_RISK_LANDING_PAGE.md`
- `docs/01_profiles/STANDARD_BUSINESS_WEBSITE.md`
- `docs/01_profiles/WEB_APPLICATION.md`
- `docs/plans/WB-019-create-initial-profile-layer.md`

## Read-only scope

- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/03_templates/`
- `docs/plans/WB-018-plan-profile-layer.md`

## Out of scope

- adapters
- examples
- tool-specific rules
- vendor-specific assumptions
- framework-specific assumptions
- product-specific examples
- editing core governance files
- editing templates

## Deliverables

- `docs/01_profiles/README.md`
- `docs/01_profiles/LOW_RISK_LANDING_PAGE.md`
- `docs/01_profiles/STANDARD_BUSINESS_WEBSITE.md`
- `docs/01_profiles/WEB_APPLICATION.md`
- Work Block closeout with checks and residual risks.

## Acceptance criteria

- [ ] `README.md` defines profile purpose, authority boundaries, profile list, and selection guidance.
- [ ] `LOW_RISK_LANDING_PAGE.md` defines simplified lifecycle depth without removing required decisions or approvals.
- [ ] `STANDARD_BUSINESS_WEBSITE.md` defines standard lifecycle depth and escalation behavior.
- [ ] `WEB_APPLICATION.md` defines extended lifecycle depth and specialist-trigger behavior.
- [ ] Each profile defines profile ID, purpose, intended use, default risk tier, lifecycle depth, artifact rules, review/verification requirements, approval gates, evidence requirements, stop conditions, and prohibited omissions.
- [ ] Profiles preserve lifecycle stage intent, approval gates, failure routes, ownership, and risk baselines.
- [ ] Profiles do not create adapters, examples, or product-specific filled content.
- [ ] Changed files remain inside the approved write-set.
- [ ] No core governance or template files are edited.

## Risks

- Profiles may accidentally weaken the baseline lifecycle by treating combined artifacts as removed decisions.
- Profiles may accidentally become examples if they include filled project content.
- The boundary between standard and extended profiles may be ambiguous without clear escalation triggers.

## Checks and evidence

- Direct read of created profile files.
- Compare changed files against approved write-set.
- Search for tool-, vendor-, framework-, hosting-, and product-specific leakage if useful.

## Stop conditions

- Build requires changing core governance files.
- Build requires adapter-specific instructions.
- Build requires examples or filled project content.
- Build requires tool, vendor, framework, or hosting assumptions.

## Plan

1. Create the profile index.
2. Create the three profile contracts from WB-018.
3. Check changed-file scope and leakage.
4. Close this Work Block and route to Review.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Planning -> Build | Approved WB-019 | Chat request: `подтверждаю выполнение WB-019 — Create Initial Profile Layer` | Create initial profile layer |
| 2026-06-24 | Orchestrator | Build | Work Block opened | `docs/plans/WB-019-create-initial-profile-layer.md` | Create profile files |

## Closeout

- Final status:
- Artifacts created or changed:
- Files changed:
- Checks run:
- Review verdict:
- Verification verdict:
- Deviations:
- Residual risks:
- Required decisions:
- Next owner/action:
