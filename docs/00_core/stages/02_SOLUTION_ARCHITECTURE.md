# Stage: 2 Solution Architecture

## Purpose

Decide the technical approach and identify data, API, backend, auth, security,
integration, operational, compliance, and external-contract constraints before
UX, planning, or implementation depends on them.

## Responsible role

Architecture Producer or Architecture Analyst acting as Producer.

## Supporting roles

- Product Owner for business trade-off decisions.
- Security, Data, Backend, Frontend, Operations, Legal, or Accessibility
  Specialists when their domains are affected.
- Orchestrator for routing, risk classification, and dependency propagation.

## Required inputs

| Artifact | Required status | Why required |
| --- | --- | --- |
| Project Brief | Approved | Defines business scope, users, constraints, and acceptance authority. |

## Preconditions

- Product scope and success criteria are approved.
- Architecture questions are bounded by the approved Project Brief.
- Required domain specialists are identified for high-risk triggers.
- No implementation begins before dependent architecture decisions are approved.

## Allowed activities

- Select technical approach and system boundaries.
- Identify data, API, backend, frontend, auth, integration, operations, and
  compliance constraints.
- Record alternatives, trade-offs, risk classification, and required controls.
- Produce the Solution Brief.

## Required outputs

| Artifact or result | Owner | Canonical path pattern |
| --- | --- | --- |
| Solution Brief | Architecture Owner | `docs/03_templates/architecture/SOLUTION_BRIEF.md` when templates exist; otherwise the approved Work Block names the path. |

## Output owner

Architecture Owner owns the technical decision meaning. Owner retains business
risk acceptance for material or high-risk decisions.

## Acceptance criteria

- The technical approach is explicit and traceable to the approved Project Brief.
- Affected data, API, auth, security, integration, operational, and compliance
  constraints are recorded.
- Alternatives and trade-offs are documented when material.
- Risk tier and required controls are identified.
- Downstream UX, design, planning, and build constraints are clear.

## Checks and evidence

- Architecture review against Project Brief and known constraints.
- Specialist review for affected high-risk domains.
- Risk tier assessment against `RISK_TIERING.md`.
- Dependency impact check against `ARTIFACT_REGISTRY.md`.

## Approver and gate

Owner or explicitly delegated Architecture Authority approves architecture
within delegated scope. Owner retains material business and residual-risk
acceptance.

## Failure routes

| Failure class | Return stage | Required action |
| --- | --- | --- |
| Product requirements are wrong or insufficient | Product Definition | Revise Project Brief and supersede affected architecture work. |
| Architecture decision is incomplete | Solution Architecture | Revise Solution Brief. |
| High-risk domain lacks specialist review | Solution Architecture | Obtain qualified specialist review before approval. |
| Architecture changes downstream assumptions | Reconsider Required | Route affected artifacts through dependency review. |

## Risks

- Encoding product decisions as architecture assumptions.
- Omitting security, data, or operational constraints.
- Choosing an implementation tool instead of defining a capability.
- Allowing downstream work to rely on unapproved architecture.

## Stop conditions

- Required domain authority is missing.
- Architecture requires secrets, production access, migrations, auth, payments,
  or deployment changes without explicit approval.
- The approved Product Brief cannot support the architecture decision.

## Next allowed stages

- UX when architecture constraints needed for user flows and states are approved.
- Implementation Planning when product, architecture, UX, and design inputs are
  ready.
- Product Definition when requirements are invalid or insufficient.
