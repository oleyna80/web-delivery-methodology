# Work Block: WB-006 — Verify Concrete Stage Contracts

## Status

In Verification

## Lifecycle stage

Verification

## Objective

Verify the concrete Stage Contract index and stage files created by WB-004 after WB-005 Review returned `APPROVE`.

## Business reason

Concrete Stage Contracts should pass independent Verification before profiles, adapters, templates, or examples rely on them as stable core authority.

## Role

Verifier / Documentation Analyst

## Profile

Repository maintenance / core documentation verification

## Expected final result

Verification Report with `PASS` or `FAIL`, evidence, limitations, residual risks, and next action.

## Inputs and authority

| Input | Status/version | Authority |
| --- | --- | --- |
| `docs/plans/WB-004-create-concrete-stage-contracts.md` | Complete | Subject Build Work Block |
| `docs/plans/WB-005-review-concrete-stage-contracts.md` | Complete / `APPROVE` | Review gate authority |
| `docs/00_core/STAGE_INDEX.md` | Current main | Subject artifact |
| `docs/00_core/stages/*.md` | Current main | Subject artifacts |
| Owner approval in chat | Approved | Authority to open and execute this Verification Work Block |

## Approved write-set

- `docs/plans/WB-006-verify-concrete-stage-contracts.md`

## Read-only scope

- `README.md`
- `PROJECT_MAP.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STATE_MACHINE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `docs/00_core/STAGE_INDEX.md`
- `docs/00_core/stages/*.md`
- `docs/plans/WB-004-create-concrete-stage-contracts.md`
- `docs/plans/WB-005-review-concrete-stage-contracts.md`
- repository comparison metadata and search output

## Out of scope

- editing Stage Contracts
- applying WB-005 findings
- creating profiles
- creating adapters
- creating templates
- creating examples
- adding tool-specific or product-specific rules
- changing lifecycle architecture, state vocabulary, role authority, approval authority, artifact ownership, or risk tiers
- adding application code, dependencies, secrets, deployment automation, or provider configuration

## Deliverables

- Verification verdict for the concrete Stage Contract set.
- Evidence for each verification criterion.
- Residual risk record and next recommended Work Block.

## Acceptance criteria

- [ ] `WB-005` Review Report exists and verdict is `APPROVE`.
- [ ] `STAGE_INDEX.md` lists stages 0–10 exactly once with canonical names.
- [ ] Every listed stage file exists.
- [ ] Stage files contain required Stage Contract sections.
- [ ] Changed files from WB-004 are limited to the approved write-set, plus recorded WB-005 and WB-006 plan artifacts.
- [ ] Search finds no vendor/tool/profile/adapter/application/deployment leakage terms introduced into core stage contracts.
- [ ] WB-005 non-blocking findings are recorded as residual risks or next-work candidates, not silently ignored.

## Risks

- Verification may not prove full semantic correctness of every stage contract line.
- GitHub search may not provide full directory-tree proof; direct file reads and commit comparison are used as compensating evidence.

## Checks and evidence

- Direct file reads for review report, index, representative stage files, and WB-004 closeout.
- Commit comparison for changed-file scope.
- Search for vendor/tool leakage terms.
- Search or direct reads for stage coverage and required headings.

## Stop conditions

- Review verdict is not `APPROVE`.
- Stage coverage is incomplete.
- Required stage files are missing.
- Evidence shows edits outside approved write-set.
- Evidence shows profile, adapter, template, example, application, deployment, or vendor-specific content was added.

## Plan

1. Verify WB-005 review verdict.
2. Verify stage index and file coverage.
3. Verify changed-file scope.
4. Verify leakage and residual-risk handling.
5. Record `PASS` or `FAIL` and closeout.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-23 | Owner | Review -> Verification | Approved WB-006 | Chat approval for WB-005 recording and transition to WB-006 | Execute Verification |
| 2026-06-23 | Orchestrator | Verification | Work Block opened | `docs/plans/WB-006-verify-concrete-stage-contracts.md` | Verify concrete Stage Contracts |

## Verification report

- Verdict:
- Evidence:
- Limitations:
- Residual risks:

## Closeout

- Final status:
- Artifacts created or changed:
- Files changed:
- Checks run:
- Review verdict: `APPROVE` from WB-005
- Verification verdict:
- Deviations:
- Residual risks:
- Required decisions:
- Next owner/action:
