# Work Block: WB-009 — Supplement Build Stage Risk Wording Correction

## Status

In Progress

## Lifecycle stage

Build

## Objective

Apply a bounded correction for WB-008 finding F-001 in `06_BUILD.md` and optionally tighten WB-008 finding F-002 in `07_REVIEW.md`.

## Business reason

WB-008 found that the Build stage risk and stop-condition wording lost direct traceability to named risk triggers in `RISK_TIERING.md`. The wording must be corrected before the concrete Stage Contract wording supplement can proceed to Verification.

## Role

Producer / Documentation Maintainer

## Profile

Repository maintenance / core documentation supplement

## Expected final result

`06_BUILD.md` restores explicit traceability to named approval-gated risk categories or `RISK_TIERING.md` triggers. `07_REVIEW.md` Stage Result wording is optionally tightened to preserve changed files, evidence, checks, deviations, and risks.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-008-review-concrete-stage-contract-wording-supplement.md` | Complete / `SUPPLEMENT` | Review findings source |
| `docs/00_core/RISK_TIERING.md` | Current main | Risk trigger authority |
| `docs/00_core/stages/06_BUILD.md` | Current main | Primary subject file |
| `docs/00_core/stages/07_REVIEW.md` | Current main | Optional secondary subject file |
| Owner approval in chat | Approved | Authority to execute this bounded supplement |

## Approved write-set

- `docs/00_core/stages/06_BUILD.md`
- `docs/00_core/stages/07_REVIEW.md`
- `docs/plans/WB-009-supplement-build-stage-risk-wording-correction.md`

## Read-only scope

- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/STATE_MACHINE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/plans/WB-008-review-concrete-stage-contract-wording-supplement.md`

## Out of scope

- editing any stage file except `06_BUILD.md` and `07_REVIEW.md`
- editing existing core governance files
- creating profiles
- creating adapters
- creating templates
- creating examples
- changing lifecycle architecture, state vocabulary, role authority, approval authority, artifact ownership, or risk tiers

## Deliverables

- `06_BUILD.md` wording correction resolving WB-008 F-001.
- Optional `07_REVIEW.md` wording tightening resolving WB-008 F-002.
- Work Block closeout with checks and residual risks.

## Acceptance criteria

- [ ] `06_BUILD.md` names concrete approval-gated categories or directly references `RISK_TIERING.md` triggers in Risks and Stop conditions.
- [ ] `06_BUILD.md` no longer relies only on broad phrases like sensitive areas or restricted-scope work.
- [ ] `07_REVIEW.md` Stage Result wording, if changed, again mentions changed files, evidence, checks, deviations, and risks.
- [ ] Changed files remain inside the approved write-set.
- [ ] No core governance file is edited.
- [ ] No profile-, adapter-, template-, example-, product-, or application-specific behavior is added.

## Risks

- Overcorrecting the wording could duplicate too much of `RISK_TIERING.md`.
- Under-correcting the wording could leave mechanical traceability weak.

## Checks and evidence

- Direct read of `06_BUILD.md` affected sections after edit.
- Direct read of `07_REVIEW.md` affected section after edit if changed.
- Compare changed files against approved write-set.
- Search for broad unresolved wording if useful.

## Stop conditions

- Correction requires changing `RISK_TIERING.md` or other governance files.
- Correction requires lifecycle or authority changes.
- Correction requires profile-, adapter-, template-, example-, product-, or application-specific content.

## Plan

1. Read current `06_BUILD.md` and `07_REVIEW.md`.
2. Correct `06_BUILD.md` Risks and Stop conditions to restore explicit risk-trigger traceability.
3. Tighten `07_REVIEW.md` Stage Result wording if safe.
4. Run checks and close this Work Block.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-23 | Owner | Review -> Build | Approved WB-009 | Chat request: `WB-009 — Supplement Build Stage Risk Wording Correction` | Execute bounded supplement |
| 2026-06-23 | Orchestrator | Build | Work Block opened | `docs/plans/WB-009-supplement-build-stage-risk-wording-correction.md` | Correct Build risk wording |

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
