# Concrete Stage Contract Index

## Purpose

This index maps every canonical lifecycle stage to its concrete Stage Contract.
`LIFECYCLE.md` remains the canonical lifecycle map. `STAGE_CONTRACT.md` remains
the reusable contract standard. The files below instantiate that standard for
stages 0–10.

## Coverage

| ID | Stage | Concrete Stage Contract |
| --- | --- | --- |
| 0 | Intake | [`stages/00_INTAKE.md`](stages/00_INTAKE.md) |
| 1 | Product Definition | [`stages/01_PRODUCT_DEFINITION.md`](stages/01_PRODUCT_DEFINITION.md) |
| 2 | Solution Architecture | [`stages/02_SOLUTION_ARCHITECTURE.md`](stages/02_SOLUTION_ARCHITECTURE.md) |
| 3 | UX | [`stages/03_UX.md`](stages/03_UX.md) |
| 4 | UI Design | [`stages/04_UI_DESIGN.md`](stages/04_UI_DESIGN.md) |
| 5 | Implementation Planning | [`stages/05_IMPLEMENTATION_PLANNING.md`](stages/05_IMPLEMENTATION_PLANNING.md) |
| 6 | Build | [`stages/06_BUILD.md`](stages/06_BUILD.md) |
| 7 | Review | [`stages/07_REVIEW.md`](stages/07_REVIEW.md) |
| 8 | Verification | [`stages/08_VERIFICATION.md`](stages/08_VERIFICATION.md) |
| 9 | Release Handoff | [`stages/09_RELEASE_HANDOFF.md`](stages/09_RELEASE_HANDOFF.md) |
| 10 | Improvement | [`stages/10_IMPROVEMENT.md`](stages/10_IMPROVEMENT.md) |

## Authority rules

- Stage files do not replace `LIFECYCLE.md`; they instantiate its stages.
- Stage files do not replace `STAGE_CONTRACT.md`; they use its required fields.
- Profiles may specialize depth and artifact combinations, but must preserve the
  stage intent, approval gates, and failure routes declared here.
- Adapters may map tools to roles and activities, but must not change stage
  authority or lifecycle order.
- If a stage file conflicts with `LIFECYCLE.md`, `STATE_MACHINE.md`,
  `ROLE_CONTRACTS.md`, `APPROVAL_MATRIX.md`, or `ARTIFACT_REGISTRY.md`, the
  conflict must be routed through Review and Reconsider Required before any
  dependent profile or adapter uses it.

## Review checklist

- Every stage from `LIFECYCLE.md` appears exactly once.
- Every listed file exists.
- Every stage file includes the required fields from `STAGE_CONTRACT.md`.
- Required inputs, outputs, approvers, and failure routes align with core files.
- No profile-specific, adapter-specific, tool-specific, vendor-specific, or
  application implementation rules are introduced in these contracts.
