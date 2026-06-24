# Adapter Contract

## Purpose

This contract defines the required structure, boundaries, and constraints for every future adapter in `docs/02_adapters/`.

Adapters map tools or execution environments to the methodology. They do not redefine the methodology.

## Contract status

This file is the governance contract for future adapters.

A concrete adapter is not authoritative unless:

- it follows this contract;
- it is created by an approved Work Block;
- it passes Review;
- it passes Verification;
- it appears in `ADAPTER_INDEX.md` as authoritative.

## Required adapter structure

Every concrete adapter must include the following sections.

### Adapter metadata

Required fields:

- Adapter ID.
- Adapter name.
- Adapter type or category.
- Status.
- Supported tool or execution-environment category.
- Producing Work Block.
- Review Work Block.
- Verification Work Block.

### Purpose

State what methodology problem the adapter solves.

The purpose must describe methodology mapping, not product implementation.

### Supported profiles

List supported profiles from `docs/01_profiles/`.

For each profile, state whether the adapter is:

- supported;
- supported with limitations;
- unsupported.

### Supported lifecycle stages

List lifecycle stages the adapter may support.

For each stage, state:

- whether the adapter may be read-only;
- whether it may write;
- which role it may perform;
- which gate or approval must exist before use.

### Supported roles

Map adapter use to core roles only.

Allowed core roles are those defined in `ROLE_CONTRACTS.md`.

If the adapter uses a specialist label, state the underlying core role.

The adapter must not create new approval authority.

### Permitted read scope

Define what the adapter may read.

Read scope should be expressed as artifact classes or repository paths, not as private secrets or environment-specific values.

### Permitted write scope

Define what the adapter may write when write access is explicitly granted by a Work Block.

The adapter must not assume write access by default.

The active Work Block always overrides the adapter with a narrower write-set when needed.

### Prohibited actions

State what the adapter must not do.

At minimum, every adapter must prohibit:

- changing files outside the approved write-set;
- changing core governance unless the Work Block is explicitly for that purpose;
- changing profiles or templates unless explicitly approved;
- storing secrets, credentials, tokens, keys, private endpoints, or deployment credentials;
- defining model routing or provider-selection policy;
- executing restricted actions without Owner approval;
- reviewing or verifying its own produced result as independent assurance;
- silently expanding scope;
- treating runtime logs or chat history as approval evidence.

### Evidence returned

Define the evidence the adapter must return after use.

Typical evidence includes:

- files read;
- files changed;
- checks performed;
- findings or outputs produced;
- limitations;
- deviations;
- residual risks;
- required next decision.

### Review and Verification independence

State how separation of duties is preserved.

If the same tool or environment can support multiple roles, the adapter must still require a recorded role transition and must disclose prior participation that could compromise independence.

A produced output cannot be independently reviewed or verified by the same actor/session when independence is required.

### Risk-tier limitations

State which risk tiers the adapter may support.

For Tier 2 or Tier 3 work, state the additional controls, Owner approvals, specialist reviews, or preflight checks required.

No adapter may lower risk-tier controls.

### Owner approval requirements

State when Owner approval is required before the adapter may proceed.

At minimum, Owner approval is required for:

- release or deployment decisions;
- destructive actions;
- restricted actions;
- accepting material residual risk;
- business-scope changes;
- sensitive or regulated work.

### Stop conditions

State conditions that require stopping and returning to the Orchestrator.

At minimum, stop when:

- required inputs are missing;
- branch or candidate state differs from the Work Block;
- write-set is unclear;
- required approval is missing;
- secret or credential exposure is detected;
- scope expands beyond the adapter's supported profile or risk tier;
- checks cannot be performed;
- independence is compromised.

### Handoff format

Define the structured return format for the adapter.

A handoff should include:

- role performed;
- stage supported;
- inputs read;
- artifacts created or changed;
- evidence;
- checks;
- deviations;
- risks;
- required next action.

### Known limitations

State known limits of the adapter.

Limitations must not be hidden in prose when they affect safety, quality, authority, or repeatability.

### Compatibility notes

State compatibility with:

- core lifecycle;
- role contracts;
- risk tiering;
- approval matrix;
- profiles;
- templates;
- Work Block contract.

## Global adapter rules

### Core authority rule

Core governance outranks every adapter.

An adapter may add constraints but may not remove or weaken core constraints.

### Profile authority rule

Profiles define lifecycle depth. An adapter may not skip a stage required by the selected profile.

### Work Block authority rule

The active Work Block defines the actual assignment.

An adapter only describes what is generally possible. The Work Block grants what is actually permitted.

### Least authority rule

When there is uncertainty, use the narrowest read scope, narrowest write-set, lowest execution authority, and strongest review requirement.

### Separation-of-duties rule

A tool, session, actor, or team that produced a result must not provide independent Review or Verification for that same result when independence is required.

### No secrets rule

Adapters must not store, request, or expose secrets, credentials, tokens, keys, private endpoints, or deployment credentials.

### No model-routing rule

Adapters must not define model routing, provider-selection policy, pricing policy, or account-specific execution policy.

### No deployment-credential rule

Adapters must not store deployment credentials or operational environment details.

### No implementation rule

Adapters describe methodology mapping only. They do not contain application implementation instructions.

## Adapter lifecycle

A concrete adapter follows this lifecycle:

1. Plan the adapter.
2. Build the adapter file.
3. Review the adapter file.
4. Verify the adapter file.
5. Add or confirm it in `ADAPTER_INDEX.md` as authoritative.
6. Use it only through bounded Work Blocks.

## Minimum Review questions for adapters

A Reviewer should check:

- Does the adapter stay subordinate to core governance?
- Does it preserve role authority and separation of duties?
- Does it preserve profile requirements?
- Does it define read scope, write scope, evidence, and stop conditions?
- Does it avoid secrets, credentials, model routing, deployment credentials, and implementation content?
- Does it avoid granting independent assurance to a producer of the same result?

## Minimum Verification checks for adapters

A Verifier should check:

- all required sections exist;
- prohibited content is absent;
- supported roles map to core roles;
- supported stages map to lifecycle stages;
- supported profiles exist;
- risk-tier limits are explicit;
- Owner approval requirements are explicit;
- stop conditions are explicit;
- index entry matches the adapter file.
