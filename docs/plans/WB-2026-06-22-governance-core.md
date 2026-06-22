# Work Block: Governance Core

## Status

Supplement Required

## Lifecycle stage

Review

## Objective

Define capability-based role contracts, approval authority, and risk tiers for
the Web Delivery Methodology before profiles, adapters, and document templates
are created.

## Business reason

The lifecycle already defines stages and state transitions, but safe execution
also requires explicit separation of duties, named approval owners, and a
repeatable way to select process depth from delivery risk.

## Role

- Owner: approved this Work Block.
- Orchestrator: owns the contract and canonical audit trail.
- Coder: writes only the approved documentation subset.
- Reviewer: performs a separate read-only governance consistency review.
- Verifier: performs separate read-only structural checks.

## Profile

`methodology-governance`

## Expected final result

- Roles are defined by responsibility rather than product name.
- No producing role approves its own independent Review or Verification.
- Every material artifact, scope change, risk acceptance, and release decision
  has a named authority.
- Risk tier determines required process, roles, evidence, and approval gates.
- Profiles may add controls but cannot weaken the core governance rules.

## Inputs and authority

- Owner confirmation in the active session.
- `docs/00_core/LIFECYCLE.md`
- `docs/00_core/STATE_MACHINE.md`
- `docs/00_core/STAGE_CONTRACT.md`
- `docs/00_core/WORK_BLOCK_CONTRACT.md`
- `docs/00_core/ARTIFACT_REGISTRY.md`

## Approved write-set

Orchestrator-only:

- `docs/plans/WB-2026-06-22-governance-core.md`

Coder subset:

- `docs/00_core/ROLE_CONTRACTS.md`
- `docs/00_core/APPROVAL_MATRIX.md`
- `docs/00_core/RISK_TIERING.md`
- `README.md`
- `PROJECT_MAP.md`

## Out of scope

- Profiles, adapters, stage templates, and examples
- Changes to the existing lifecycle, state machine, stage contract, Work Block
  contract, or artifact registry
- Application code, dependencies, automation, global agent configuration,
  other projects, commit, or push

## Deliverables

- Canonical role and separation-of-duties contract
- Canonical approval matrix and delegation rules
- Canonical risk classification and control matrix
- Updated repository navigation and current-status summary

## Acceptance criteria

- [ ] Owner, Orchestrator, Producer/Builder, Reviewer, Verifier, Specialist, and
      Release Operator responsibilities are explicit.
- [ ] Role definitions are tool-agnostic.
- [ ] One actor cannot produce and independently approve the same result.
- [ ] Subagents return structured results and do not own canonical audit writes.
- [ ] Approval authority is explicit for every lifecycle gate.
- [ ] Scope expansion, risk acceptance, and release require named human authority.
- [ ] Risk tiers have objective selection criteria.
- [ ] The highest applicable risk tier governs the Work Block.
- [ ] Every tier defines minimum contract, review, verification, and approval.
- [ ] Restricted work cannot execute autonomously.
- [ ] README and PROJECT_MAP identify all governance documents.
- [ ] Reviewer verdict is `APPROVE` or all findings are resolved.
- [ ] Verifier verdict is `PASS`.

## Risks

- Too many role names could make small projects difficult to operate.
- A matrix that treats an AI agent as final business authority would be unsafe.
- Subjective risk classification could allow accidental process downgrades.
- Tool-specific assumptions would undermine future adapters.

## Checks and evidence

- Cross-document terminology search for roles, decisions, gates, and tiers
- Every lifecycle stage represented in the approval matrix
- Every risk tier has required process and approval behavior
- No core document names a specific AI product as required authority
- No write outside the approved set
- Markdown structure and whitespace checks

## Stop conditions

Stop for Owner approval if work requires:

- changing an existing canonical contract;
- creating profiles, adapters, or templates;
- allowing autonomous release or restricted operations;
- changing another project;
- commit or push.

## Plan

1. Define minimal roles and strict separation of duties.
2. Map lifecycle gates and sensitive decisions to approval authority.
3. Define risk-tier selection and minimum controls.
4. Update navigation.
5. Run separate Review and Verification.

## Execution log

Only the Orchestrator updates this table.

| Date/time | Actor/role | Stage | Outcome/verdict | Files/evidence | Risks/next action |
| --- | --- | --- | --- | --- | --- |
| 2026-06-22 | Owner | Approval | Approved governance documentation Work Block | Owner confirmation in active session | Implement only roles, approvals, risk tiers, and navigation |
| 2026-06-22 | Orchestrator | Spec | Defined scope, criteria, risks, and separation requirements | This Work Block | Assign one Coder to approved subset |
| 2026-06-22 | Coder | Implementation | Created role contracts, approval matrix, risk tiering, and navigation updates | Five files in approved Coder subset; whitespace and file inventory checks | Proceed to separate read-only governance Review |
| 2026-06-22 | Reviewer | Review | SUPPLEMENT: risk tier is mandatory in new governance but absent from existing Work Block contract and Definition of Ready | Cross-document `risk tier` search against lifecycle and Work Block contract | Stop for Owner approval to expand write-set and synchronize canonical contracts |

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
