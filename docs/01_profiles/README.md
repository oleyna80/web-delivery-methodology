# Profile Layer

## Purpose

Profiles define lifecycle depth for different delivery types. A profile may simplify, standardize, or extend how the canonical lifecycle is applied, but it must not change the core methodology authority.

Profiles answer:

- which stages are required;
- which artifacts are required;
- which artifacts may be combined;
- which gates, reviews, verifications, and approvals are required;
- when work must escalate to a higher risk tier or fuller lifecycle path.

## Authority boundaries

Profiles may:

- combine adjacent artifacts when canonical sections, semantic ownership, approval evidence, and downstream traceability remain explicit;
- require additional artifacts for higher-complexity delivery;
- raise risk tier or add controls;
- define profile-specific readiness and evidence requirements.

Profiles must not:

- remove lifecycle stage intent;
- remove approval gates;
- remove failure routes;
- make ownership or approval implicit;
- lower the risk baseline defined by `docs/00_core/RISK_TIERING.md`;
- override role authority from `docs/00_core/ROLE_CONTRACTS.md`;
- change artifact ownership from `docs/00_core/ARTIFACT_REGISTRY.md`;
- add tool-, vendor-, framework-, hosting-, or execution-environment assumptions.

## Initial profiles

| Profile | Purpose | Default risk posture | Use when |
| --- | --- | --- | --- |
| `LOW_RISK_LANDING_PAGE` | Simplified lifecycle for low-risk information-only pages | Tier 1 unless a higher-tier trigger appears | Work is mostly content, layout, and visual presentation with low operational impact |
| `STANDARD_BUSINESS_WEBSITE` | Standard lifecycle for business websites and content workflows | Tier 1 with explicit escalation | Work includes multiple pages, content structure, visual design, and moderate workflow decisions |
| `WEB_APPLICATION` | Extended lifecycle for interactive applications | Tier 1 minimum, often Tier 2 when triggered | Work includes interaction flows, accounts, backend logic, data models, integrations, or operational constraints |

## Profile selection procedure

1. Start from the lowest plausible profile.
2. Check the objective against `docs/00_core/RISK_TIERING.md`.
3. If a higher-tier trigger appears, use the higher-risk controls even if the profile name seems simple.
4. If a required decision does not fit the selected profile, move to a fuller profile instead of omitting the decision.
5. Record the chosen profile and risk tier in the Work Block.

## Combined artifact rule

A profile may combine artifacts only when:

- every canonical section remains identifiable;
- semantic ownership and approval remain unchanged;
- downstream consumers can locate the required information;
- the profile declares the combined canonical path;
- dependency review is preserved when upstream decisions change.

## Review and Verification rule

Every profile that produces a non-trivial outcome requires independent Review and Verification proportional to risk. A simplified profile may reduce artifact count, but it must not label a self-check as independent assurance.

## Current status

This profile layer is a methodology contract layer. It does not contain adapters, filled examples, tool configuration, product implementation, deployment instructions, or agent-specific rules.
