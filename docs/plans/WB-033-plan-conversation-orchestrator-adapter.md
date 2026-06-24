# WB-033 — Plan Conversation Orchestrator Adapter

## Status

Complete

## Lifecycle stage

Implementation Planning

## Objective

Plan the next concrete adapter after `REPOSITORY_CODING_AGENT`: a Conversation Orchestrator adapter for conversational assistant environments that coordinate Work Blocks, route roles, prepare prompts, receive evidence, and maintain methodology flow without silently taking Builder, Reviewer, Verifier, Owner, or Release authority.

## Business reason

The Repository Coding Agent adapter is now verified and authoritative for repository-aware coding assignments. The next missing adapter is the conversational orchestration layer used to coordinate methodology work outside direct repository editing.

A Conversation Orchestrator adapter is needed before examples because examples should show at least two distinct adapter roles:

- a conversational Orchestrator that plans, routes, and records decisions;
- a repository-aware coding agent that performs bounded repository work.

## Role

Orchestrator / Methodology Planner

## Profile

Repository maintenance / adapter planning

## Expected final result

A bounded plan for the Conversation Orchestrator adapter, including adapter purpose, proposed path, supported roles, lifecycle stages, read/write posture, evidence handling, stop conditions, risks, and next Work Block.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/02_adapters/ADAPTER_INDEX.md` | Current main | Candidate category and authoritative adapter state |
| `docs/02_adapters/ADAPTER_CONTRACT.md` | Current main | Required concrete adapter structure |
| `docs/02_adapters/REPOSITORY_CODING_AGENT.md` | Verified | Existing concrete adapter boundary |
| `docs/plans/WB-032-promote-repository-coding-agent-adapter.md` | Complete | Previous promotion Work Block |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and independence authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage authority |
| `docs/00_core/WORK_BLOCK_CONTRACT.md` | Current main | Work Block authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls |
| Owner approval in chat | Approved | Authority to execute WB-033 |

## Approved write-set

- `docs/plans/WB-033-plan-conversation-orchestrator-adapter.md`

## Read-only scope

- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
- `docs/plans/WB-032-promote-repository-coding-agent-adapter.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/01_profiles/`
- `docs/03_templates/`

## Out of scope

- creating the concrete adapter file
- editing `ADAPTER_INDEX.md`
- creating examples
- changing `REPOSITORY_CODING_AGENT.md`
- changing core governance, profiles, or templates
- adding vendors, products, model names, provider policy, account assumptions, installation commands, runtime setup instructions, deployment instructions, secrets, or credentials
- granting Owner, Builder, Reviewer, Verifier, or Release authority to a conversational assistant by default

## Selected concrete adapter to plan

`Conversation Orchestrator adapter`

## Proposed future adapter file

`docs/02_adapters/CONVERSATION_ORCHESTRATOR.md`

## Adapter category definition

A Conversation Orchestrator adapter maps a conversational assistant environment to methodology coordination work.

It may support:

- Work Block planning;
- role routing;
- prompt preparation for external agents or reviewers;
- receiving and summarizing Review or Verification reports;
- recording Work Block artifacts when explicitly assigned and approved;
- maintaining next-action continuity;
- detecting missing approvals, scope drift, role conflicts, or independence problems.

It must not act as a universal execution role.

## Rationale for selection

This adapter should be created next because it represents the coordination layer that surrounds repository coding work.

Without this adapter, the methodology has a verified repository coding adapter but no verified conversational control layer to:

- decide which Work Block should open next;
- keep roles separate;
- avoid self-review or self-verification;
- create bounded prompts for external tools;
- treat chat history as evidence rather than authority;
- prevent conversational convenience from bypassing repository governance.

## Supported lifecycle stages to plan

The future adapter should initially cover:

- Intake support: collect and structure user intent without making unapproved commitments;
- Product Definition support: draft or refine product artifacts when assigned;
- Solution Architecture support: route architecture questions to Architecture Owner or specialist when needed;
- UX support: frame UX tasks and route to UX/design roles;
- UI Design support: prepare design prompts and receive design reports, without becoming Design Authority;
- Implementation Planning: plan Work Blocks, define read/write scopes, identify risk tier and required checks;
- Build support: prepare prompts or instructions, but not perform repository Build unless explicitly assigned through a different adapter and disclosed role transition;
- Review support: receive external Review reports and record them, but not independently Review its own produced candidate;
- Verification support: receive external Verification reports and record them, but not independently Verify its own produced candidate;
- Release Handoff support: prepare handoff summaries, but not authorize release or deployment;
- Improvement support: collect retrospective evidence and route next Work Blocks.

## Supported roles to plan

The future adapter should map to core roles only.

Primary support:

- Orchestrator-support: plan and route Work Blocks, maintain stage continuity, identify next action.
- Producer: create planning, prompt, or documentation artifacts only when the active Work Block grants write permission.
- Specialist: analyze methodology state or repository evidence without approval authority.

Read-only conditional support:

- Reviewer: only for artifacts it did not produce and only when independence is not compromised.
- Verifier: only for artifacts it did not produce and only when independence is not compromised.

Not supported by default:

- Owner: cannot grant Owner approval, accept business risk, or approve releases.
- Builder: cannot perform repository edits by default; repository Build belongs to the Repository Coding Agent adapter or another explicitly assigned adapter.
- Release Operator: cannot execute release/deployment by default.

## Relationship to Repository Coding Agent adapter

`REPOSITORY_CODING_AGENT` is now the verified adapter for repository-aware coding assignments.

The Conversation Orchestrator adapter should coordinate such assignments but must not silently inherit repository write authority.

If the same environment or assistant switches from Orchestrator-support to Producer, Builder, Reviewer, or Verifier, the Work Block must record the role transition and assess independence.

## Supported profiles to plan

The future adapter should support all verified profiles with limitations:

- `LOW_RISK_LANDING_PAGE`: may coordinate simplified low-risk website workflows and external agent prompts.
- `STANDARD_BUSINESS_WEBSITE`: may coordinate standard website lifecycle, handoffs, and Review/Verification evidence routing.
- `WEB_APPLICATION`: may coordinate planning and evidence routing only with stronger controls for architecture, data, auth, security, integration, dependency, configuration, operations, restricted actions, and production readiness.

The adapter must not use profile selection to skip required approvals, reviews, verification, or risk controls.

## Risk-tier posture

Default posture:

- Tier 1: supported for planning, documentation, prompt preparation, evidence intake, and routing with explicit Work Block scope.
- Tier 2: supported only with explicit risk identification, stronger evidence, and specialist/Owner routing where triggered.
- Tier 3: not autonomously executable. The adapter may coordinate routing but cannot perform or authorize restricted actions.

The adapter must not lower risk-tier controls.

## Required concrete adapter constraints

The future concrete adapter must:

- follow `ADAPTER_CONTRACT.md` section structure;
- remain subordinate to core governance, profiles, templates, verified adapters, and active Work Block;
- state that chat history is evidence, not approval authority;
- state that it cannot grant Owner approval;
- state that it cannot silently create or change repository files outside an approved write-set;
- state that it cannot independently Review or Verify work it produced or coordinated in a way that compromises independence;
- state that it must disclose role transitions;
- state that it must route missing approvals, unclear scope, branch/repository drift, or independence problems back to Orchestrator/Owner;
- avoid all vendor/product/model/provider-specific assumptions;
- avoid setup, runtime, deployment, credential, or implementation instructions.

## Required future index handling

The next Build Work Block may update `ADAPTER_INDEX.md` only to add the concrete adapter as `Draft` or equivalent non-authoritative status.

The adapter must not be marked authoritative until it passes Review and Verification.

## Proposed future Work Block: WB-034

`WB-034 — Create Conversation Orchestrator Adapter`

Stage: Build

Objective: Create the Conversation Orchestrator adapter file and add a non-authoritative Draft entry to `ADAPTER_INDEX.md`.

Expected result: Conversation Orchestrator adapter draft exists and is ready for Review.

Approved write-set:

- `docs/02_adapters/CONVERSATION_ORCHESTRATOR.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-034-create-conversation-orchestrator-adapter.md`

Read-only scope:

- `docs/plans/WB-033-plan-conversation-orchestrator-adapter.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/02_adapters/REPOSITORY_CODING_AGENT.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/RISK_TIERING.md`
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

- [x] Next concrete adapter category is selected.
- [x] Selection rationale is documented.
- [x] Proposed adapter path is documented.
- [x] Relationship to `REPOSITORY_CODING_AGENT` is documented.
- [x] Supported roles and lifecycle stages are scoped.
- [x] Supported profiles and risk-tier posture are scoped.
- [x] Future adapter constraints are documented.
- [x] Future index handling is documented.
- [x] Future Build Work Block write-set is defined.
- [x] No concrete adapter is created in this Work Block.
- [x] `ADAPTER_INDEX.md` is not edited in this Work Block.
- [x] Examples remain deferred.

## Risks

- A conversational adapter can accidentally become a universal assistant policy rather than a bounded methodology adapter.
- It can blur Orchestrator, Producer, Builder, Reviewer, Verifier, and Owner roles.
- It can treat chat history as approval evidence.
- It can bypass repository authority by giving broad instructions without a Work Block.
- It can make Review/Verification independence appear stronger than it is.

## Mitigations

- Keep the adapter role-based and methodology-specific.
- Require active Work Block assignment for any write-capable action.
- Treat chat history as evidence only, never approval authority.
- Preserve separation of duties and require role-transition disclosure.
- Keep repository Build under the verified Repository Coding Agent adapter unless explicitly reassigned.
- Require external Review and Verification before promotion.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Release Handoff -> Implementation Planning | Approved WB-033 | Chat confirmation: `Согласен. Начинаем` | Plan Conversation Orchestrator adapter |
| 2026-06-24 | Orchestrator | Implementation Planning | Selected next concrete adapter category | Conversation Orchestrator adapter | Recommend WB-034 |

## Closeout

- Final status: Complete
- Artifacts created or changed: Conversation Orchestrator adapter planning Work Block
- Files changed:
  - `docs/plans/WB-033-plan-conversation-orchestrator-adapter.md`
- Checks run:
  - used verified Repository Coding Agent adapter as existing adapter boundary
  - used `ADAPTER_CONTRACT.md` as concrete adapter structure authority
  - used `ADAPTER_INDEX.md` candidate list and authority rules
  - confirmed no concrete adapter was created
  - confirmed examples remain deferred
- Review verdict: not required for this planning note unless Owner requests independent Review
- Verification verdict: not required for this planning note unless Owner requests independent Verification
- Deviations: none
- Residual risks:
  - Conversation Orchestrator adapter still requires Build, Review, Verification, and Promotion
  - concrete adapter must remain generic and non-authoritative until verified
  - examples remain deferred
- Required decisions: Owner approval to open `WB-034 — Create Conversation Orchestrator Adapter`
- Next owner/action: open `WB-034 — Create Conversation Orchestrator Adapter` if Owner approves
