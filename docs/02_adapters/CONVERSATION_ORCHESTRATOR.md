# Conversation Orchestrator Adapter

## Adapter metadata

| Field | Value |
| --- | --- |
| Adapter ID | `CONVERSATION_ORCHESTRATOR` |
| Adapter name | Conversation Orchestrator Adapter |
| Adapter type or category | Conversational coordination environment |
| Status | Draft |
| Supported tool or execution-environment category | Conversational assistant environment for methodology coordination, Work Block planning, role routing, prompt preparation, and evidence intake |
| Producing Work Block | `WB-034 — Create Conversation Orchestrator Adapter` |
| Review Work Block | Pending |
| Verification Work Block | Pending |

## Purpose

This adapter maps a conversational assistant environment to methodology coordination work.

It supports Work Block planning, role routing, prompt preparation, evidence intake, report summarization, next-action continuity, and detection of missing approvals, scope drift, role conflicts, or independence problems.

This adapter describes methodology mapping only. It does not define tool setup, account setup, runtime setup, deployment setup, provider policy, model routing, credentials, or application implementation.

It is not a universal assistant policy and does not grant execution authority by default.

## Supported profiles

| Profile | Support status | Limits |
| --- | --- | --- |
| `LOW_RISK_LANDING_PAGE` | Supported with limitations | May coordinate simplified low-risk website workflows, prepare bounded prompts, and receive evidence when the selected profile remains low-risk. Escalate on Tier 2 or Tier 3 triggers. |
| `STANDARD_BUSINESS_WEBSITE` | Supported with limitations | May coordinate standard website lifecycle, handoffs, prompts, Review evidence, and Verification evidence. Escalate for architecture contracts, sensitive data, external dependencies, production-readiness changes, difficult rollback, or restricted actions. |
| `WEB_APPLICATION` | Supported with stronger controls | May coordinate planning and evidence routing only with stronger controls for architecture, data, auth, security, integration, dependency, configuration, operations, restricted actions, and production readiness. |

The adapter must not use a profile to skip lifecycle stages, approvals, reviews, verification, or risk controls required by that profile.

## Supported lifecycle stages

| Lifecycle stage | Support | Role posture | Required gate or approval |
| --- | --- | --- | --- |
| 0 Intake | Supported | Orchestrator-support or Specialist when assigned | Owner or Orchestrator defines intake scope |
| 1 Product Definition | Supported with limitations | Producer, Specialist, or Orchestrator-support when assigned | Product Owner approval remains external to the adapter |
| 2 Solution Architecture | Routing and documentation support only | Specialist, Producer, or Orchestrator-support when assigned | Architecture Owner approval remains external to the adapter |
| 3 UX | Routing and documentation support only | Specialist, Producer, or Orchestrator-support when assigned | UX ownership remains external to the adapter |
| 4 UI Design | Prompting and evidence intake support only | Specialist, Producer, or Orchestrator-support when assigned | Design Authority approval remains external to the adapter |
| 5 Implementation Planning | Supported | Orchestrator-support, Producer, or Specialist when assigned | Active Work Block defines scope, risk, checks, and next action |
| 6 Build | Prompting and coordination support only by default | Orchestrator-support or Producer when assigned | Repository edits require a separate explicit write-set and suitable adapter/role assignment |
| 7 Review | Evidence intake or read-only Review only | Reviewer only if independence is not compromised | Reviewed candidate must be frozen; prior participation must be disclosed |
| 8 Verification | Evidence intake or read-only Verification only | Verifier only if independence is not compromised | Verification candidate and expected checks must be defined |
| 9 Release Handoff | Summary and routing support only | Orchestrator-support, Producer, or Specialist when assigned | Owner authorization required for release decisions or restricted operations |
| 10 Improvement | Supported | Orchestrator-support, Producer, or Specialist when assigned | Owner or Orchestrator defines improvement route |

The adapter does not own product, architecture, UX, design, build, review, verification, or release decisions. It may coordinate or produce supporting artifacts only within the active Work Block role and permissions.

## Supported roles

This adapter maps only to core roles defined by `ROLE_CONTRACTS.md`.

| Core role | Support | Constraints |
| --- | --- | --- |
| Owner | Not supported | The adapter may ask for Owner approval or record it as evidence, but cannot grant Owner approval, accept business risk, or approve releases. |
| Orchestrator | Support only | May help plan Work Blocks, route roles, identify next action, prepare prompts, and record evidence when explicitly assigned. It must not silently expand scope or treat chat history as approval evidence. |
| Producer | Supported with explicit assignment | May create planning, prompt, summary, or documentation artifacts only within approved write-set. |
| Builder | Not supported by default | May coordinate Build prompts but must not perform repository edits unless a separate Work Block grants explicit Builder role, write-set, and role-transition disclosure. |
| Specialist | Supported | May analyze methodology state, reports, or repository evidence without approval authority. |
| Reviewer | Supported read-only with independence limits | May Review only if it did not produce or coordinate the candidate in a way that compromises independence. |
| Verifier | Supported read-only with independence limits | May Verify only if it did not produce or coordinate the candidate in a way that compromises independence. |
| Release Operator | Not supported by default | Release execution requires a separate Owner-authorized Work Block and is outside this adapter's default posture. |

Specialist labels do not create approval authority.

## Permitted read scope

The adapter may read only the artifacts, messages, reports, repository paths, or evidence sources granted by the active Work Block.

Typical permitted read scope may include:

- user-provided requirements or constraints;
- active Work Block and upstream Work Blocks;
- methodology governance files;
- selected profile files;
- selected template files;
- adapter files relevant to routing;
- external Review or Verification reports provided by the user;
- repository evidence needed to decide next action.

Chat history, runtime logs, and external reports are evidence sources. They are not approval authority unless the active Work Block or Owner explicitly records them as approval evidence.

Read scope must not include secrets, credentials, tokens, private endpoints, deployment credentials, or private operational configuration unless explicitly handled by a higher-risk Owner-approved process outside this adapter.

## Permitted write scope

The adapter never assumes write access by default.

Write access exists only when the active Work Block grants an explicit write-set.

When write access is granted, this adapter may write only planning, prompt, summary, routing, or Work Block documentation artifacts inside the approved write-set.

Repository implementation changes are outside this adapter's default posture and should be routed to a suitable verified adapter or separately assigned Builder role.

The adapter must report exact files changed when it writes repository files and must preserve unrelated and pre-existing work.

## Prohibited actions

The adapter must not:

- grant Owner approval;
- accept business risk on behalf of the Owner;
- approve release or deployment decisions;
- act as Builder by default;
- perform repository edits without explicit active Work Block write-set;
- silently inherit write authority from another adapter;
- silently expand scope;
- treat chat history, runtime logs, or external reports as approval authority;
- independently Review a candidate it produced or coordinated in a way that compromises independence;
- independently Verify a candidate it produced or coordinated in a way that compromises independence;
- change core governance unless the Work Block is explicitly for that purpose;
- change profiles or templates unless explicitly approved;
- store, request, or expose secrets, credentials, tokens, keys, private endpoints, deployment credentials, or private operational configuration;
- define model routing, provider-selection policy, pricing policy, or account-specific execution policy;
- add installation commands or runtime setup steps;
- add deployment instructions or deployment credentials;
- execute restricted actions without explicit Owner approval;
- mark an adapter authoritative before Review and Verification;
- create examples unless a separate Work Block explicitly scopes example creation;
- create application implementation instructions unless the active Work Block is an implementation-planning or implementation-support step and grants that scope.

## Evidence returned

After any assignment, the adapter must return structured evidence appropriate to the role and stage.

Minimum evidence for coordination assignments:

- role performed;
- lifecycle stage;
- user intent or input summarized;
- artifacts or reports read;
- selected profile, if any;
- risk tier or risk triggers identified;
- proposed next Work Block;
- missing approvals or missing evidence;
- role-separation concerns;
- limitations;
- residual risks;
- required next action.

Minimum evidence for write-capable documentation assignments:

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

Minimum evidence when receiving external Review or Verification reports:

- source of report;
- reported role;
- reported verdict;
- files or artifacts reviewed;
- findings, if any;
- residual risks;
- recommended next action;
- whether the report is recorded as evidence or requires additional verification.

## Review and Verification independence

The same actor, session, or team that produced or materially coordinated a result must not independently Review or Verify that same result when independence is required.

If a conversational assistant switches roles, the Work Block must record:

- the previous role;
- the previous contribution;
- whether the assistant produced, coordinated, reviewed, or verified the candidate;
- whether independence is compromised;
- whether a different reviewer or verifier is required.

Review and Verification must be read-only unless a separate documentation-only evidence path is explicitly approved.

## Risk-tier limitations

| Risk tier | Support | Required controls |
| --- | --- | --- |
| Tier 1 | Supported | Clear active Work Block, bounded read scope, explicit write-set for writes, checks or evidence expectations, and acceptance criteria. |
| Tier 2 | Supported with extra controls | Explicit risk identification, stronger evidence, specialist routing where triggered, Owner routing where required, and clearer rollback or recovery expectations when relevant. |
| Tier 3 | Not autonomously executable | May coordinate routing only. Requires explicit Owner approval, narrowed Work Block, specialist review, preflight checks where applicable, and no autonomous restricted execution. |

The adapter may add constraints but must not lower risk-tier controls.

## Owner approval requirements

Owner approval is required before the adapter records or routes any work involving:

- release or deployment decisions;
- destructive actions;
- restricted actions;
- accepting material residual risk;
- business-scope changes;
- sensitive or regulated work;
- role reassignment that could compromise independence;
- any action where core governance, profile contracts, or risk tiering require Owner authority.

The adapter may ask for approval, record explicit approval evidence, or route approval requests. It cannot grant Owner approval.

## Stop conditions

Stop and route back to the Owner or Orchestrator when:

- required inputs are missing;
- active Work Block is missing or unclear;
- role assignment is unclear;
- read scope is unclear;
- write-set is unclear;
- repository state or candidate state differs from the Work Block;
- required approval is missing;
- chat history is being treated as approval without explicit approval evidence;
- secret, credential, token, private endpoint, or deployment credential exposure is detected;
- scope expands beyond the selected profile or risk tier;
- checks or evidence cannot be obtained;
- external report evidence is incomplete or contradictory;
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
- Evidence received:
- Approved write-set:
- Files changed:
- Checks performed:
- Findings or routing decision:
- Approval evidence:
- Role-transition disclosure:
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
- It does not make a conversational assistant safe for independent assurance when it produced or materially coordinated the candidate.
- It does not authorize repository writes by default.
- It does not authorize restricted actions.
- It does not replace Owner, Product Owner, Architecture Owner, Design Authority, Builder, Reviewer, Verifier, or Release Operator authority.

## Compatibility notes

- Core lifecycle: compatible; the adapter maps to lifecycle coordination without removing stage intent.
- Role contracts: compatible; it maps to core roles only and preserves separation of duties.
- Risk tiering: compatible; it may add controls but may not lower controls.
- Approval matrix: compatible; it does not grant approval authority.
- Profiles: compatible with all verified profiles subject to stated limitations and risk controls.
- Templates: compatible; it may produce or inspect template-based artifacts only within active Work Block scope.
- Work Block contract: compatible; the active Work Block grants actual read scope, write-set, checks, and approvals.
- Repository Coding Agent adapter: compatible; repository Build work should be routed to `REPOSITORY_CODING_AGENT` unless a separate Work Block explicitly assigns another suitable adapter or role.

## Current status

Draft.

This adapter is not authoritative until it passes independent Review and Verification and `ADAPTER_INDEX.md` records it as verified or authoritative according to index rules.
