# WB-028 — Plan First Concrete Adapter

## Status

Complete

## Lifecycle stage

Implementation Planning

## Objective

Plan the first concrete adapter to be created after the Adapter layer governance foundation passed Verification in WB-027.

## Business reason

The Adapter governance foundation is now verified. The next step is to choose and scope the first concrete adapter without creating it yet. The first adapter should exercise the adapter contract against the repository-based workflow used by this methodology while preserving core authority, profile contracts, template semantics, Work Block boundaries, and separation of duties.

## Role

Orchestrator / Methodology Planner

## Profile

Repository maintenance / adapter planning

## Expected final result

A bounded plan for the first concrete adapter, including the selected adapter category, rationale, proposed path, future write-set, scope, supported roles, supported stages, constraints, risks, and next Work Block.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-027-verify-adapter-layer-contract-and-index.md` | Complete / `PASS` | Adapter governance verification gate |
| `docs/02_adapters/README.md` | Governance foundation | Adapter layer authority and boundaries |
| `docs/02_adapters/ADAPTER_CONTRACT.md` | Governance foundation | Required concrete adapter structure |
| `docs/02_adapters/ADAPTER_INDEX.md` | Governance foundation | Adapter status and index rules |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and independence authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls |
| `docs/01_profiles/` | Verified | Profile compatibility authority |
| Owner approval in chat | Approved | Authority to plan first concrete adapter |

## Approved write-set

- `docs/plans/WB-028-plan-first-concrete-adapter.md`

## Read-only scope

- `docs/plans/WB-027-verify-adapter-layer-contract-and-index.md`
- `docs/02_adapters/README.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/01_profiles/`
- `docs/03_templates/`

## Out of scope

- creating the concrete adapter file
- editing `ADAPTER_INDEX.md`
- creating examples
- adding vendors, products, model names, provider policy, account assumptions, installation commands, runtime setup instructions, deployment instructions, secrets, or credentials
- changing core governance, profiles, or templates

## Selected first concrete adapter

`Repository Coding Agent adapter`

## Proposed future adapter file

`docs/02_adapters/REPOSITORY_CODING_AGENT.md`

## Rationale for selection

This adapter should be created first because repository-aware coding environments are already central to the methodology workflow:

- they can implement bounded repository changes;
- they can create or revise documentation artifacts;
- they can inspect repository files for Review or Verification;
- they require strict read/write boundaries;
- they expose the most important separation-of-duties risks;
- they exercise the Adapter Contract more completely than a purely conversational or design-only adapter.

## Adapter category definition

A Repository Coding Agent adapter maps a repository-aware coding environment to bounded methodology assignments in a repository.

It may support roles such as:

- Builder, when explicitly assigned a Build Work Block;
- Producer, when explicitly assigned to create or revise documentation artifacts;
- Reviewer, only in read-only mode and only when independence is not compromised;
- Verifier, only in read-only mode and only when independence is not compromised;
- Specialist, when asked for domain analysis without write authority.

It must not create new role authority.

## Supported lifecycle stages to plan

The future adapter should initially cover:

- Implementation Planning, read-only or documentation-producing support;
- Build, bounded write-set execution;
- Review, read-only assessment with `APPROVE`, `SUPPLEMENT`, or `RECONSIDER`;
- Verification, read-only evidence reproduction with `PASS` or `FAIL`;
- Release Handoff support, read-only unless separately assigned as Release Operator under Owner authorization.

The adapter should not directly own Product Definition, UX, UI Design, or Release decisions. It may inspect or produce supporting artifacts only when the active Work Block grants that role and scope.

## Supported profiles to plan

The future adapter should support all verified profiles with limitations:

- `LOW_RISK_LANDING_PAGE`: supported for bounded content, design-implementation, and documentation changes when the selected profile allows the simplified path.
- `STANDARD_BUSINESS_WEBSITE`: supported for bounded site structure, content, implementation, review, and verification tasks.
- `WEB_APPLICATION`: supported with stronger controls for architecture, data, auth, security, integration, dependency, configuration, operational, restricted-action, and production-readiness triggers.

## Risk-tier posture

Default posture:

- Tier 1: allowed when the active Work Block grants clear read scope, write-set, checks, and acceptance criteria.
- Tier 2: allowed only with explicit additional controls, specialist review where triggered, and clear rollback or recovery expectations when relevant.
- Tier 3: not autonomously executable. Requires explicit Owner approval, narrowed Work Block, specialist review, and preflight checks where applicable.

The adapter must never lower risk-tier controls.

## Required concrete adapter constraints

The future concrete adapter must:

- follow `ADAPTER_CONTRACT.md` section structure;
- remain subordinate to core governance, profiles, templates, and the active Work Block;
- map capabilities only to core roles;
- state that write access is never assumed by default;
- state that actual write access is granted only by active Work Block write-set;
- require exact changed files and evidence after write-capable assignments;
- require read-only mode for Review and Verification;
- prevent the same actor/session from independently reviewing or verifying its own produced result when independence is required;
- require role transition disclosure when the same environment is reused for different roles;
- stop on branch drift, unclear write-set, missing approval, secret exposure, failed checks, scope expansion, or compromised independence;
- avoid all vendor/product/model/provider-specific assumptions.

## Required future index handling

The next Build Work Block may update `ADAPTER_INDEX.md` only to add the concrete adapter as `Draft` or equivalent non-authoritative status.

The adapter must not be marked authoritative until it passes Review and Verification.

## Proposed future Work Block: WB-029

`WB-029 — Create Repository Coding Agent Adapter`

Stage: Build

Objective: Create the first concrete adapter file for repository-aware coding environments and add a non-authoritative Draft entry to `ADAPTER_INDEX.md`.

Expected result: Repository Coding Agent adapter draft exists and is ready for Review.

Approved write-set:

- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-029-create-repository-coding-agent-adapter.md`

Read-only scope:

- `docs/plans/WB-027-verify-adapter-layer-contract-and-index.md`
- `docs/plans/WB-028-plan-first-concrete-adapter.md`
- `docs/02_adapters/README.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/01_profiles/`
- `docs/03_templates/`

Out of scope:

- vendors, products, model names, provider policy, account assumptions;
- installation commands;
- runtime setup steps;
- deployment instructions;
- secrets or credentials;
- examples;
- core/profile/template changes;
- marking the adapter authoritative before Review and Verification.

Risk tier: Tier 1 documentation build

## Acceptance criteria

- [x] First concrete adapter category is selected.
- [x] Selection rationale is documented.
- [x] Proposed adapter path is documented.
- [x] Supported roles and stages are scoped.
- [x] Supported profiles and risk-tier posture are scoped.
- [x] Future adapter constraints are documented.
- [x] Future index handling is documented.
- [x] Future Build Work Block write-set is defined.
- [x] No concrete adapter is created in this Work Block.
- [x] `ADAPTER_INDEX.md` is not edited in this Work Block.
- [x] Examples remain deferred.

## Risks

- A repository coding adapter can easily become too broad and start acting as a universal execution policy.
- Review and Verification independence can be compromised if the same session produces and then reviews/verifies the same result.
- Tier 2/Tier 3 work can be under-controlled if the adapter does not explicitly route to Owner approvals and specialist review.
- The adapter can accidentally include vendor/product/model-specific operational assumptions.

## Mitigations

- Keep the adapter generic and category-based.
- Require active Work Block permission for every write-capable assignment.
- Require read-only mode for Review and Verification.
- Require role transition disclosure.
- Require explicit stop conditions.
- Add only a Draft/non-authoritative index entry during the Build step.
- Defer authoritative status until Review and Verification pass.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Verification -> Implementation Planning | Approved WB-028 | Chat request: `начинай WB-028 — Plan First Concrete Adapter` | Plan first concrete adapter |
| 2026-06-24 | Orchestrator | Implementation Planning | Selected first adapter category | Repository Coding Agent adapter | Recommend WB-029 |

## Closeout

- Final status: Complete
- Artifacts created or changed: first concrete adapter planning Work Block
- Files changed:
  - `docs/plans/WB-028-plan-first-concrete-adapter.md`
- Checks run:
  - used WB-027 `PASS` as adapter-governance gate
  - used `ADAPTER_CONTRACT.md` as concrete adapter structure authority
  - used `ADAPTER_INDEX.md` candidate list and authority rules
  - confirmed no concrete adapter was created
  - confirmed examples remain deferred
- Review verdict: not required for this planning note unless Owner requests independent Review
- Verification verdict: not required for this planning note unless Owner requests independent Verification
- Deviations: none
- Residual risks:
  - first concrete adapter still requires Build, Review, and Verification
  - concrete adapter must remain generic and non-authoritative until verified
  - examples remain deferred
- Required decisions: Owner approval to open `WB-029 — Create Repository Coding Agent Adapter`
- Next owner/action: open `WB-029 — Create Repository Coding Agent Adapter` if Owner approves
