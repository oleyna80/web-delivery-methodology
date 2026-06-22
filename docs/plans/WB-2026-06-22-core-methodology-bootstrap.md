# Work Block: Core Methodology Bootstrap

## Status

Complete

## Stage

Verification

## Objective

Create the standalone Web Delivery Methodology project and define its
tool-agnostic lifecycle, execution states, stage contract, Work Block contract,
and canonical artifact registry.

## Role

- Owner: approves scope and future expansion.
- Orchestrator: owns this Work Block and stage transitions.
- Coder: creates only the approved documentation files.
- Reviewer: performs a separate read-only consistency review.
- Verifier: performs a separate read-only structural verification.

## Profile

`methodology-bootstrap`

## Expected final result

A readable and internally consistent core that both the Owner and an agent
Orchestrator can follow. Every lifecycle stage has an explicit purpose, inputs,
outputs, gate, and failure route. Tool-specific behavior is deferred to future
adapters.

## Approved write-set

- `.gitignore`
- `AGENTS.md`
- `README.md`
- `PROJECT_MAP.md`
- `docs/plans/WB-2026-06-22-core-methodology-bootstrap.md`
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STATE_MACHINE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`
- repository metadata created by `git init`

## Out of scope

- Lifecycle profiles
- Product-specific templates and examples
- Antigravity, Codex, Claude Code, or other tool adapters
- Agent installation or global configuration
- Changes to other projects
- Dependencies, application code, deployment, commit, or push

## Risks

- Excessive ceremony could make the simplified profile unusable.
- Ambiguous artifact ownership could recreate multiple sources of truth.
- Coupling core documents to current tools would reduce portability.
- Defining templates before the lifecycle stabilizes would create rework.

## Checks

- Every lifecycle stage declares input, output, gate, and failure route.
- State names and transitions agree across core documents.
- Stage Contract and Work Block Contract have distinct responsibilities.
- Every canonical artifact has one owner and one planned template path.
- Core documentation contains no mandatory product/tool dependency.
- All links and referenced current files resolve.
- Git diff remains inside the approved write-set.

## Stop conditions

Stop for Owner approval if implementation requires:

- profiles, adapters, or detailed stage templates;
- changing another repository;
- adding dependencies or executable automation;
- an architecture that makes a specific AI product mandatory;
- commit or push.

## Acceptance criteria

- [x] Project structure and maintenance rules are documented.
- [x] Canonical lifecycle is defined.
- [x] Simplified and extended delivery are supported through future profiles.
- [x] Backend, data, API, auth, security, and integration decisions occur before
      dependent implementation.
- [x] Review failure and verification failure have explicit return routes.
- [x] Each stage has a defined input and output artifact or result.
- [x] Agent results use a standard result envelope.
- [x] Artifact registry prevents competing sources of truth.
- [x] Reviewer verdict is `APPROVE` or all findings are resolved.
- [x] Verifier verdict is `PASS`.

## Execution log

Only the Orchestrator updates this canonical task audit trail.

| Date | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-22 | Owner | Approval | Approved creation of the standalone project and documentation | Owner request in active session | Bootstrap the core only; agent wrappers remain deferred |
| 2026-06-22 | Orchestrator | Spec | Defined bootstrap scope, contracts, checks, and stop conditions | This Work Block | Assign one Coder to the approved documentation write-set |
| 2026-06-22 | Coder | Implementation | Created the repository entry points and five core methodology documents within the approved write-set | Ten approved files and repository metadata; `git status --short`; file inventory | Proceed to separate read-only consistency Review |
| 2026-06-22 | Reviewer | Review | SUPPLEMENT: Work Block template omits three canonical execution states | `STATE_MACHINE.md` compared with `WORK_BLOCK_CONTRACT.md`; portability and whitespace searches | Add `Supplement Required`, `Reconsider Required`, and `Verified`, then repeat Review |
| 2026-06-22 | Coder | Implementation/Fix | Added all missing canonical states to the Work Block status field | `docs/00_core/WORK_BLOCK_CONTRACT.md` | Repeat read-only Review |
| 2026-06-22 | Reviewer | Review | APPROVE: core documents are internally consistent after supplement | Canonical-state coverage, portability search, whitespace search, and repository status | Proceed to independent read-only Verification |
| 2026-06-22 | Verifier | Verification | PASS: structure, lifecycle coverage, contracts, links, portability, branch, and exact file set verified | Read-only shell assertions; repository contains exactly ten approved files on `main` | Close bootstrap WB without commit or push |

## Closeout

- Final status: Complete
- Files changed: ten files in the approved write-set plus Git repository
  metadata created by `git init`; no other project was modified.
- Checks run: exact file inventory and count; lifecycle stage count; required
  lifecycle columns; Stage Result fields; review and verification transition
  assertions; current-link checks; portability and whitespace searches; branch
  and repository status.
- Review verdict: APPROVE after one resolved supplement.
- Verification verdict: PASS.
- Residual risks: profiles, adapters, concrete templates, role contracts,
  approval matrix, risk tiers, and worked examples do not yet exist. Planned
  template paths are registry declarations, not usable files.
- Next owner/action: approve the next Work Block for role, approval, and risk
  governance before creating profiles and templates.
