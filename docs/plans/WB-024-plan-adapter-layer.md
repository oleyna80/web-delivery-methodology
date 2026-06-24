# Work Block: WB-024 — Plan Adapter Layer

## Status

Complete

## Lifecycle stage

Implementation Planning

## Objective

Plan the Adapter layer under `docs/02_adapters/` after the Profile layer passed Verification in WB-023.

## Business reason

The Template layer and Profile layer are now verified. The next methodology layer is the Adapter layer, which maps the core methodology, profiles, templates, roles, and stage gates to concrete tools or execution environments without changing methodology authority or storing operational configuration.

## Role

Orchestrator / Methodology Planner

## Profile

Repository maintenance / adapter layer planning

## Expected final result

A bounded plan for creating the initial Adapter layer contract and index, while deferring concrete tool adapters until the adapter contract is reviewed and verified.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-023-verify-initial-profile-layer.md` | Complete / `PASS` | Profile-layer verification gate |
| `PROJECT_MAP.md` | Current main | Planned layer map |
| `docs/00_core/ROLE_CONTRACTS.md` | Current main | Role and permission authority |
| `docs/00_core/LIFECYCLE.md` | Current main | Stage authority |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk controls |
| `docs/00_core/WORK_BLOCK_CONTRACT.md` | Current main | Work Block authority |
| `docs/01_profiles/` | Verified | Delivery-depth contracts |
| `docs/03_templates/` | Verified | Artifact skeleton foundation |
| Owner approval in chat | Approved | Authority to plan the Adapter layer |

## Approved write-set

- `docs/plans/WB-024-plan-adapter-layer.md`

## Read-only scope

- `PROJECT_MAP.md`
- `docs/plans/WB-023-verify-initial-profile-layer.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/01_profiles/`
- `docs/03_templates/`

## Out of scope

- creating concrete adapters
- creating examples
- editing core governance files
- editing profiles
- editing templates
- storing secrets, credentials, tokens, keys, or private endpoint values
- adding model routing rules
- adding deployment credentials
- adding application implementation
- adding tool installation instructions that act as operational setup for a real project

## Current repository facts

- `PROJECT_MAP.md` defines `docs/02_adapters/` as mappings for tools and execution environments.
- `PROJECT_MAP.md` also states that planned paths are not authoritative until the creating Work Block is approved and files exist.
- Repository boundaries exclude application implementation, agent global configuration, secrets, model routing, and deployment credentials.
- `WB-023` verified the Profile layer as ready for Adapter planning.
- `ROLE_CONTRACTS.md` defines that roles describe authority and responsibility, not products, job titles, or specific people; a human, agent, or team may perform a role only inside an explicit Work Block and with granted permissions.
- `ROLE_CONTRACTS.md` also requires separation of duties: the same actor must not produce a result and then act as independent Reviewer or Verifier for that same result.

## Adapter layer definition

An Adapter is a methodology mapping from core roles, lifecycle stages, profile contracts, artifact templates, and Work Block boundaries to a specific tool or execution environment.

An Adapter answers:

- which methodology role a tool/environment can support;
- which stages the tool/environment can participate in;
- which artifacts it can read;
- which files or artifacts it may write, if any;
- what evidence it must return;
- what it must never do;
- when human Owner approval or Orchestrator routing is required;
- which profile/risk-tier combinations it is safe for.

## Adapter layer boundaries

Adapters may:

- name specific tools or execution environments;
- map tool capabilities to methodology roles and stages;
- define allowed read scope and write scope patterns;
- define evidence returned by the tool;
- define tool-specific limitations and stop conditions;
- define which profile and risk-tier combinations the adapter can support;
- define handoff expectations between tools.

Adapters must not:

- override core lifecycle, role authority, approval gates, or risk tiers;
- override profile contracts;
- modify template semantics;
- store secrets, credentials, tokens, keys, private endpoint values, or deployment credentials;
- define global agent configuration;
- define model routing or provider-selection policy;
- authorize restricted actions;
- grant a tool independent Review or Verification over its own produced result;
- create filled project examples;
- create application implementation instructions.

## Distinction between layers

| Layer | Purpose | May be tool-specific? | May contain filled project content? |
| --- | --- | --- | --- |
| Core | Non-negotiable lifecycle, roles, approvals, risk, and artifact authority | No | No |
| Templates | Neutral artifact skeletons | No | No |
| Profiles | Delivery-depth contracts for project classes | No | No |
| Adapters | Tool/execution-environment mappings to the methodology | Yes, within boundaries | No |
| Examples | Completed sample artifacts demonstrating use | May reference adapter context when needed | Yes, when explicitly scoped |

## Recommended adapter contract structure

Every adapter should define:

- adapter ID and name;
- tool or execution environment category;
- purpose;
- supported profiles;
- supported lifecycle stages;
- supported roles;
- permitted read scope;
- permitted write scope;
- prohibited actions;
- evidence returned;
- Review/Verification independence rules;
- risk-tier limitations;
- Owner approval requirements;
- stop conditions;
- handoff format;
- known limitations;
- compatibility notes with templates and profiles.

## Initial adapter-layer build strategy

Do not create concrete tool adapters immediately.

First create an adapter governance layer:

- `docs/02_adapters/README.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`

Rationale:

- Adapters are the first layer that may name tools or execution environments.
- A contract is needed before adding tool-specific files to prevent leakage into secrets, deployment credentials, model routing, or application implementation.
- Review and Verification can validate the adapter contract before concrete adapters are added.

## Initial adapter categories for later planning

After the adapter contract and index are reviewed and verified, future Work Blocks may create adapters for categories such as:

1. Conversation Orchestrator adapter
   - maps a conversational assistant environment to Orchestrator, Producer, Documentation Analyst, or planning-support roles.

2. Repository Coding Agent adapter
   - maps a repository-aware coding environment to Builder, Producer, Reviewer, or Verifier roles with explicit separation of duties.

3. Local CLI Agent adapter
   - maps a terminal/local-repository execution environment to bounded Build, Review, or Verification assignments.

4. Design/Frontend Agent adapter
   - maps design-generation or frontend-focused environments to UI Design, Visual Review, and frontend Build support.

5. Connector/Repository API adapter
   - maps repository connector actions to read/write constraints, audit evidence, and Work Block file maintenance.

These are candidate categories only. They are not authoritative adapters until separate Build, Review, and Verification Work Blocks create and approve concrete adapter files.

## Recommended first concrete adapter sequence after contract verification

1. Repository Coding Agent adapter.
2. Conversation Orchestrator adapter.
3. Design/Frontend Agent adapter.
4. Connector/Repository API adapter.
5. Local CLI Agent adapter if still needed after the above.

Reasoning:

- Repository Coding Agent and Conversation Orchestrator adapters are most central to the current methodology workflow.
- Design/Frontend Agent can then map the UI Design and Visual Review path.
- Connector/Repository API adapter should be defined after the audit/write rules are already clear.
- Local CLI Agent may overlap with repository coding agents and should not be created unless the distinction is useful.

## Required constraints for the first adapter build

The first adapter build must not:

- create concrete tool adapters;
- include specific vendors, products, models, or providers beyond generic adapter categories;
- store secrets or credentials;
- include installation commands or runtime setup steps;
- modify core/profile/template files;
- create examples;
- grant execution authority outside explicit Work Blocks;
- weaken separation of duties;
- allow autonomous restricted work.

## Acceptance criteria

- [x] Adapter layer is planned after Profile-layer Verification `PASS`.
- [x] Adapter definition is stated clearly.
- [x] Adapter layer boundaries distinguish allowed tool mapping from prohibited configuration/secrets/model-routing/deployment content.
- [x] Adapter contract structure is defined.
- [x] Initial build is limited to adapter README, contract, and index.
- [x] Concrete adapters are deferred until contract/index Review and Verification.
- [x] Examples remain deferred.
- [x] Core governance, profiles, and templates remain unchanged.

## Risks

- Adapters may accidentally become operational setup guides instead of methodology mappings.
- Adapters may leak secrets, deployment details, or model-routing assumptions.
- Adapters may weaken separation of duties by allowing a tool to review or verify its own output.
- Too many concrete adapters too early may make the methodology brittle and vendor-dependent.

## Mitigations

- Build adapter contract and index before concrete adapters.
- Keep adapter files declarative and methodology-focused.
- Require every adapter to state read scope, write scope, prohibited actions, evidence, and independence limits.
- Require Review and Verification before any concrete adapter becomes authoritative.
- Defer examples until at least the adapter contract and one concrete adapter are verified.

## Recommended next Work Block

`WB-025 — Create Adapter Layer Contract and Index`

Stage: Build

Objective: Create the adapter governance files under `docs/02_adapters/` without creating concrete tool adapters.

Expected result: Adapter layer foundation with README, adapter contract, and adapter index.

Approved write-set:

- `docs/02_adapters/README.md`
- `docs/02_adapters/ADAPTER_CONTRACT.md`
- `docs/02_adapters/ADAPTER_INDEX.md`
- `docs/plans/WB-025-create-adapter-layer-contract-and-index.md`

Read-only scope:

- `PROJECT_MAP.md`
- `docs/plans/WB-023-verify-initial-profile-layer.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/01_profiles/`
- `docs/03_templates/`

Out of scope:

- concrete adapters
- examples
- tool installation instructions
- secrets or credentials
- model routing
- deployment credentials
- application implementation
- core/profile/template changes

Risk tier: Tier 1 documentation build

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-24 | Owner | Verification -> Implementation Planning | Approved WB-024 | Chat request: `подтверждаю WB-024 — Plan Adapter Layer` | Plan Adapter layer |
| 2026-06-24 | Orchestrator | Implementation Planning | Planning complete | `PROJECT_MAP.md`, `WB-023`, `ROLE_CONTRACTS.md` | Recommend WB-025 |

## Closeout

- Final status: Complete
- Artifacts created or changed: Adapter layer planning Work Block
- Files changed:
  - `docs/plans/WB-024-plan-adapter-layer.md`
- Checks run:
  - read `PROJECT_MAP.md` for planned adapter path and repository boundaries
  - read `WB-023` for Profile-layer readiness and immutability evidence
  - read `ROLE_CONTRACTS.md` for role authority and separation-of-duties constraints
- Review verdict: not required for this planning note unless Owner requests independent Review
- Verification verdict: not required for this planning note unless Owner requests independent Verification
- Deviations: none
- Residual risks:
  - concrete adapters remain uncreated
  - adapter contract and index still require Build, Review, and Verification before concrete adapter files are safe to create
  - examples remain deferred
- Required decisions: Owner approval to open `WB-025 — Create Adapter Layer Contract and Index`
- Next owner/action: open `WB-025 — Create Adapter Layer Contract and Index` if Owner approves
