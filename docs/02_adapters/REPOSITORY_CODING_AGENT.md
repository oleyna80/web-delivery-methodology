# Repository Coding Agent Adapter

## Adapter metadata

| Field | Value |
| --- | --- |
| Adapter ID | `REPOSITORY_CODING_AGENT` |
| Adapter name | Repository Coding Agent Adapter |
| Adapter type or category | Repository-aware coding environment |
| Status | Draft |
| Supported tool or execution-environment category | Repository-aware coding environment with file inspection and bounded file-editing capability |
| Producing Work Block | `WB-029 — Create Repository Coding Agent Adapter` |
| Review Work Block | Pending |
| Verification Work Block | Pending |

## Purpose

This adapter maps a repository-aware coding environment to bounded methodology assignments in a repository.

It supports methodology work where the active Work Block grants explicit read scope, write-set, role, checks, acceptance criteria, and stop conditions.

This adapter describes methodology mapping only. It does not define tool setup, account setup, runtime setup, deployment setup, provider policy, model routing, credentials, or application implementation.

## Supported profiles

| Profile | Support status | Limits |
| --- | --- | --- |
| `LOW_RISK_LANDING_PAGE` | Supported with limitations | Use for bounded documentation, content, visual implementation, and verification work when the profile remains low-risk and information-only or low impact. Escalate on Tier 2 or Tier 3 triggers. |
| `STANDARD_BUSINESS_WEBSITE` | Supported with limitations | Use for bounded website structure, content, implementation, review, and verification work. Escalate for architecture contracts, sensitive data, external dependencies, production-readiness changes, difficult rollback, or restricted actions. |
| `WEB_APPLICATION` | Supported with stronger controls | Use only through explicit Work Blocks with architecture, data, auth, security, integration, dependency, configuration, operational, restricted-action, and production-readiness controls where triggered. |

The adapter must not use a profile to skip lifecycle stages, approvals, reviews, verification, or risk controls required by that profile.

## Supported lifecycle stages

| Lifecycle stage | Support | Role posture | Required gate or approval |
| --- | --- | --- | --- |
| 0 Intake | Read-only support | Specialist or Orchestrator-support only | Owner or Orchestrator defines intake scope |
| 1 Product Definition | Documentation support only | Producer or Specialist when assigned | Product Owner approval remains external to the adapter |
| 2 Solution Architecture | Documentation or analysis support only | Producer or Specialist when assigned | Architecture Owner approval remains external to the adapter |
| 3 UX | Documentation or analysis support only | Producer or Specialist when assigned | UX ownership remains external to the adapter |
| 4 UI Design | Documentation or implementation support only | Producer, Specialist, or Builder when assigned | Design Authority approval remains external to the adapter |
| 5 Implementation Planning | Supported | Producer, Specialist, or Orchestrator-support when assigned | Active Work Block defines scope |
| 6 Build | Supported | Builder only when write-set is explicit | Active Work Block grants write-set and checks |
| 7 Review | Supported read-only | Reviewer only if independence is not compromised | Reviewed candidate must be frozen |
| 8 Verification | Supported read-only | Verifier only if independence is not compromised | Review must be approved or routed as required |
| 9 Release Handoff | Read-only support by default | Specialist, Producer, or Release-support only when assigned | Owner authorization required for release decisions or restricted operations |
| 10 Improvement | Documentation support | Producer or Specialist when assigned | Owner or Orchestrator defines improvement route |

The adapter does not own product, architecture, UX, design, or release decisions. It may support those stages only within the active Work Block role and permissions.

## Supported roles

This adapter maps only to core roles defined by `ROLE_CONTRACTS.md`.

| Core role | Support | Constraints |
| --- | --- | --- |
| Owner | Not supported | The adapter may provide recommendations but cannot grant Owner approval or accept business risk. |
| Orchestrator | Support only | The adapter may help draft Work Blocks or inspect repository state, but cannot silently expand scope or treat chat/runtime history as approval evidence. |
| Producer | Supported | May create or revise documentation artifacts only within approved write-set. |
| Builder | Supported | May edit repository files only when an active Work Block grants explicit write-set and checks. |
| Specialist | Supported | Read-only by default; may produce analysis or recommendations within assigned scope. |
| Reviewer | Supported read-only | May review only if it did not produce the reviewed result and independence is not compromised. |
| Verifier | Supported read-only | May verify only if it did not produce the candidate and independence is not compromised. |
| Release Operator | Not supported by default | Release execution requires a separate Owner-authorized Work Block and is outside this adapter's default posture. |

Specialist labels do not create approval authority.

## Permitted read scope

The adapter may read only the artifacts, paths, or repository areas granted by the active Work Block.

Typical permitted read scope may include:

- core methodology files;
- selected profile files;
- selected template files;
- active Work Block and upstream Work Blocks;
- candidate files under Review or Verification;
- repository files needed to satisfy the assigned stage.

Read scope must be expressed as artifact classes or repository paths. It must not include secrets, credentials, tokens, private endpoints, deployment credentials, or private operational configuration unless explicitly handled by a higher-risk Owner-approved process outside this adapter.

## Permitted write scope

The adapter never assumes write access by default.

Write access exists only when the active Work Block grants an explicit write-set.

When write access is granted, the adapter may write only to the approved files or paths. The active Work Block may narrow this adapter's general capability at any time.

The adapter must report exact files changed and must preserve unrelated and pre-existing work.

## Prohibited actions

The adapter must not:

- write outside the approved write-set;
- silently expand scope;
- change core governance unless the Work Block is explicitly for that purpose;
- change profiles or templates unless explicitly approved;
- store, request, or expose secrets, credentials, tokens, keys, private endpoints, deployment credentials, or private operational configuration;
- define model routing, provider-selection policy, pricing policy, or account-specific execution policy;
- add installation commands or runtime setup steps;
- add deployment instructions or deployment credentials;
- execute restricted actions without explicit Owner approval;
- approve its own output as independent Review;
- verify its own output as independent Verification;
- treat chat history, runtime logs, or local scratch output as approval evidence;
- mark an adapter authoritative before Review and Verification;
- create examples unless a separate Work Block explicitly scopes example creation;
- create application implementation instructions unless the active Work Block is an implementation Build step for a specific project and grants that write-set.

## Evidence returned

After any assignment, the adapter must return structured evidence appropriate to the role and stage.

Minimum evidence for read-only assignments:

- role performed;
- lifecycle stage;
- files or artifacts read;
- findings, recommendations, or verdict;
- limitations;
- residual risks;
- required next action.

Minimum evidence for write-capable assignments:

- role performed;
- lifecycle stage;
- approved write-set;
- exact files changed;
- summary of changes;
- checks performed;
- evidence from checks;
- deviations;
- residual risks;
- required next action.

## Review and Verification independence

The same actor, session, or team that produced a result must not independently Review or Verify that same result when independence is required.

If the same repository-aware environment is reused for a later role, the Work Block must record:

- the previous role;
- the previous contribution;
- whether independence is compromised;
- whether a different reviewer or verifier is required.

Review and Verification must be read-only unless a separate documentation-only evidence path is explicitly approved.

## Risk-tier limitations

| Risk tier | Support | Required controls |
| --- | --- | --- |
| Tier 1 | Supported | Clear active Work Block, bounded read scope, explicit write-set for writes, required checks, and acceptance criteria. |
| Tier 2 | Supported with extra controls | Explicit additional controls, specialist review where triggered, clearer rollback or recovery expectations where relevant, and stronger evidence. |
| Tier 3 | Not autonomously executable | Requires explicit Owner approval, narrowed Work Block, specialist review, preflight checks where applicable, and no autonomous restricted execution. |

The adapter may add constraints but must not lower risk-tier controls.

## Owner approval requirements

Owner approval is required before the adapter participates in any work involving:

- release or deployment decisions;
- destructive actions;
- restricted actions;
- accepting material residual risk;
- business-scope changes;
- sensitive or regulated work;
- any action where core governance, profile contracts, or risk tiering require Owner authority.

The adapter may recommend an action but cannot grant Owner approval.

## Stop conditions

Stop and route back to the Orchestrator when:

- required inputs are missing;
- active Work Block is missing or unclear;
- read scope is unclear;
- write-set is unclear;
- candidate, branch, or repository state differs from the Work Block;
- required approval is missing;
- secret, credential, token, private endpoint, or deployment credential exposure is detected;
- scope expands beyond the selected profile or risk tier;
- checks cannot be performed;
- checks fail and no approved supplement route exists;
- independence is compromised;
- the assignment requires vendors, products, model names, provider policy, installation commands, runtime setup, deployment details, examples, or implementation content outside approved scope.

## Handoff format

The adapter should return this structure at the end of an assignment:

```markdown
## Stage Result

- Role performed:
- Lifecycle stage:
- Profile:
- Risk tier:
- Inputs read:
- Approved write-set:
- Files changed:
- Checks performed:
- Evidence:
- Deviations:
- Residual risks:
- Stop conditions encountered:
- Verdict or outcome:
- Required next action:
```

For Review, use verdicts: `APPROVE`, `SUPPLEMENT`, or `RECONSIDER`.

For Verification, use verdicts: `PASS` or `FAIL`.

## Known limitations

- This adapter is generic and does not describe a specific product or vendor workflow.
- It does not define setup, installation, runtime configuration, model selection, provider policy, deployment, or credential handling.
- It does not make a repository-aware environment safe for independent assurance when it produced the candidate under review.
- It does not authorize restricted actions.
- It does not replace Owner, Architecture Owner, Design Authority, Reviewer, Verifier, or Release Operator authority.

## Compatibility notes

- Core lifecycle: compatible; the adapter maps to lifecycle stages but does not remove stage intent.
- Role contracts: compatible; it maps to core roles only and preserves separation of duties.
- Risk tiering: compatible; it may add controls but may not lower controls.
- Approval matrix: compatible; it does not grant approval authority.
- Profiles: compatible with all verified profiles subject to stated limitations and risk controls.
- Templates: compatible; it may produce or inspect template-based artifacts only within active Work Block scope.
- Work Block contract: compatible; the active Work Block grants actual read scope, write-set, checks, and approvals.

## Current status

Draft.

This adapter is not authoritative until it passes independent Review and Verification and `ADAPTER_INDEX.md` records it as verified or authoritative according to index rules.
