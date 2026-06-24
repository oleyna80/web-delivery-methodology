# Adapter Layer

## Purpose

The Adapter layer maps the methodology to tools and execution environments without changing the methodology itself.

Adapters connect:

- core lifecycle stages;
- core roles and separation-of-duties rules;
- profile contracts;
- canonical templates;
- Work Block boundaries;
- read/write permissions;
- evidence requirements;
- stop conditions.

An adapter is not a setup guide, configuration file, prompt library, deployment recipe, product example, or implementation plan.

## Authority

Adapters are subordinate to:

1. `docs/00_core/` — lifecycle, roles, approvals, risk, state, and artifact authority.
2. `docs/01_profiles/` — delivery-depth contracts.
3. `docs/03_templates/` — canonical artifact skeletons.
4. The active Work Block — exact stage, role, read scope, write-set, checks, and approval gates.

If an adapter conflicts with core governance, profile contracts, templates, or the active Work Block, the adapter loses.

## What adapters may do

Adapters may:

- name a tool category or execution-environment category;
- map capabilities to methodology roles;
- identify supported lifecycle stages;
- identify supported profiles and risk tiers;
- define permitted read scope;
- define permitted write scope patterns;
- define expected evidence and handoff format;
- define tool-specific limitations;
- define stop conditions;
- define when Owner approval or Orchestrator routing is required.

## What adapters must not do

Adapters must not:

- override lifecycle stage intent;
- override role authority;
- override approval gates;
- lower risk-tier controls;
- override profile contracts;
- modify template semantics;
- store secrets, credentials, tokens, keys, private endpoint values, or deployment credentials;
- define model routing or provider-selection policy;
- define global agent configuration;
- define installation commands or runtime setup steps;
- authorize restricted actions;
- grant a tool independent Review or Verification over its own produced result;
- create filled project examples;
- create application implementation instructions.

## Current files

- `ADAPTER_CONTRACT.md` — required structure and constraints for every future adapter.
- `ADAPTER_INDEX.md` — authoritative index of adapter files and candidate categories.

## Current status

This layer currently contains the adapter governance foundation only.

No concrete adapter is authoritative yet.

Concrete adapters require separate Build, Review, and Verification Work Blocks before they can be used as methodology authority.

## Relationship to examples

Examples remain out of scope for this layer.

Examples may later demonstrate how a profile, adapter, and template are used together, but no example becomes authoritative merely because it references an adapter.
