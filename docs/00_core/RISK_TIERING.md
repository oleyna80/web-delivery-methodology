# Risk Tiering

## Purpose

Risk tier determines the minimum process depth, separation of duties, evidence,
and approval required for a Work Block. Classification is based on impact and
execution characteristics, not file count alone.

The highest applicable tier governs. Profiles and destination projects may
raise a tier or add controls; they may not lower this baseline without explicit
Owner risk acceptance, and restricted work cannot be downgraded for autonomous
execution.

## Classification dimensions

Assess each Work Block against:

- user, business, financial, legal, and operational impact;
- production exposure and number of affected users;
- data sensitivity and privacy impact;
- authentication, authorization, security, and abuse potential;
- reversibility and quality of rollback or recovery;
- architecture and external-contract impact;
- uncertainty, novelty, and evidence quality;
- breadth across files, systems, teams, and lifecycle stages;
- destructive capability or access to secrets;
- dependency on external services or irreversible third-party actions.

If classification is uncertain between two tiers, use the higher tier until the
uncertainty is resolved.

## Tier definitions

### Tier 0 — Trivial

Characteristics:

- local, reversible, and obvious change;
- no behavior, contract, layout, data, security, dependency, configuration, or
  production impact;
- typically a typo, comment, formatting correction, or equivalent metadata fix.

Minimum controls:

- Small Task Path permitted;
- one writer;
- exact changed-file report;
- focused check;
- independent Review optional unless destination rules require it;
- no self-check may be labelled independent assurance.

### Tier 1 — Standard

Characteristics:

- bounded feature, design, frontend, content, documentation, test, or refactor;
- understood contracts and reversible implementation;
- no high-risk domain trigger.

Minimum controls:

- full Work Block;
- approved inputs, write-set, acceptance criteria, checks, and stop conditions;
- one Producer or Builder writer;
- independent read-only Review;
- independent Verification proportional to the result;
- Owner approval for material scope changes;
- Stage Result and closeout.

### Tier 2 — High

Any of the following normally makes work High risk:

- architecture or external API contract change;
- backend business logic with material user impact;
- database schema, migration, or data transformation;
- authentication, authorization, security control, or sensitive-data handling;
- payments, orders, inventory, financial, or regulated behavior;
- new dependency, runtime configuration, infrastructure, deployment, or
  production-readiness change;
- broad cross-system refactor or difficult rollback;
- unresolved technical uncertainty with significant downstream cost.

Minimum controls:

- extended lifecycle artifacts appropriate to affected domains;
- full Work Block with explicit risk assessment;
- qualified Specialist review for each triggered domain;
- independent Review and Verification by actors not involved in production;
- Owner approval at architecture, scope, residual-risk, and release gates as
  applicable;
- test strategy including failure paths;
- rollback or recovery plan;
- affected-artifact and integration analysis;
- staged execution and explicit stop conditions.

### Tier 3 — Restricted

Restricted work includes:

- access to, disclosure of, or movement of secrets and credentials;
- destructive production operations or destructive database commands;
- irreversible third-party actions or publication;
- force push, history rewrite, deletion of unknown data, or disabling safeguards;
- production release with material financial, safety, privacy, legal, or
  availability consequence;
- actions prohibited from autonomous execution by destination policy.

Minimum controls:

- no autonomous execution;
- named human Owner authorization for the exact action, target, and timing;
- least privilege and approved access channel;
- independent domain Review and preflight Verification;
- backup, rollback, recovery, or explicit acknowledgement when recovery is
  impossible;
- human-controlled execution or observation as required by destination policy;
- durable evidence without recording secret values;
- immediate stop on drift, missing evidence, unexpected state, or exposed secret.

An autonomous agent may prepare a plan, inspect safe metadata, or produce a
read-only recommendation. It must not infer execution authority from permission
to analyze restricted work.

## Control matrix

| Control | Tier 0 | Tier 1 | Tier 2 | Tier 3 |
| --- | --- | --- | --- | --- |
| Full Work Block | Optional | Required | Required | Required |
| One writer | Required | Required | Required | Required |
| Independent Review | Optional | Required | Required | Required |
| Independent Verification | Focused self-check allowed | Required, proportional | Required with domain evidence | Required preflight plus human control |
| Specialist involvement | No | As needed | Required for triggered domains | Required |
| Owner approval before implementation | Only for sensitive scope | For material scope | Required for affected high-risk decisions | Required for exact action |
| Rollback or recovery plan | No | When relevant | Required | Required or impossibility explicitly accepted |
| Autonomous execution | Allowed within scope | Allowed within approved scope | Only for explicitly approved reversible steps | Prohibited |
| Release authority | Not applicable | Human gate when releasing | Human gate | Named human exact-action gate |

## Classification procedure

1. Describe the objective and affected systems.
2. Evaluate every classification dimension.
3. Identify all explicit Tier 2 and Tier 3 triggers.
4. Select the highest applicable tier.
5. Record rationale, required specialists, approvals, checks, and stop
   conditions in the Work Block.
6. Reassess when scope or evidence changes.

The Orchestrator proposes the tier. The Owner approves Tier 2 and Tier 3 scope
before implementation. A Reviewer or Verifier may require reclassification when
evidence contradicts the recorded tier.

## Escalation triggers

Immediately pause and reassess when work unexpectedly encounters:

- secrets, credentials, private keys, or sensitive personal data;
- production systems or live customer data;
- schema, migration, auth, payment, security, infrastructure, or deployment
  changes;
- a new dependency or external service;
- destructive or irreversible commands;
- missing rollback, test environment, or authority;
- unrelated dirty files that overlap the required write-set;
- acceptance criteria that cannot be verified safely.

The discovery of a higher-tier trigger invalidates lower-tier execution
authority until the Work Block and approvals are updated.

