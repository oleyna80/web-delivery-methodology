# Role Contracts

## Purpose

Roles describe authority and responsibility, not products, job titles, or
specific people. A human, agent, or team may perform a role only within an
explicit Work Block and only with the permissions granted there.

One actor may hold different roles in different stages. The same actor must not
produce a result and then act as its independent Reviewer or Verifier.

## Core roles

### Owner

The Owner is the accountable human authority for business scope, budget, risk
acceptance, visual approval, and release decisions.

Responsibilities:

- approve project intent, material scope, and success criteria;
- appoint or explicitly delegate decision authorities;
- accept material residual risk;
- approve sensitive or restricted work;
- authorize release, deployment, destructive actions, commit, and push when the
  destination project requires those gates;
- stop, cancel, or supersede work.

The Owner may use agent recommendations but must not delegate final authority
for restricted operations or business risk acceptance to an autonomous agent.

### Orchestrator

The Orchestrator controls workflow, not business truth.

Responsibilities:

- select the lifecycle stage, profile, and risk tier;
- create bounded Work Blocks and check Definition of Ready;
- identify inputs, roles, write ownership, acceptance criteria, checks, risks,
  stop conditions, and approval gates;
- assign read-only specialists, Reviewers, and Verifiers;
- receive structured Stage Results;
- maintain the active Work Block status, audit trail, verdicts, and closeout;
- route supplements, reconsideration, failures, and scope changes;
- prevent downstream work from using unapproved artifacts.

The Orchestrator may not silently expand scope, accept Owner-level risk, grant
its own release authority, or treat chat history as approval evidence.

### Producer

The Producer creates or revises a canonical subject artifact such as a Project
Brief, Solution Brief, UX Specification, Design Specification, content package,
or implementation plan.

Responsibilities:

- work only from approved inputs;
- preserve source authority and document assumptions;
- write only within the approved write-set;
- run producer checks;
- return a Stage Result with artifacts, evidence, deviations, and risks.

The Producer owns semantic accuracy of its output but cannot grant independent
approval to that output.

### Builder

The Builder is the sole writer for an implementation or fix step. `Coder` is a
common execution label for this role.

Responsibilities:

- implement only the approved Work Block;
- preserve unrelated and pre-existing work;
- avoid dependencies, configuration, data, security, deployment, and other
  sensitive changes unless explicitly approved;
- run the required build-level checks;
- return exact changed files, evidence, deviations, and residual risks.

The Builder does not edit the active Work Block audit trail and does not approve
its own implementation.

### Specialist

A Specialist supplies domain analysis for product, architecture, UX, design,
frontend, backend, data, security, QA, content, legal, accessibility,
operations, or another named domain.

Responsibilities:

- stay within the assigned question and read/write permission;
- identify assumptions, constraints, risks, and unresolved decisions;
- cite inspected artifacts and evidence;
- return a structured recommendation to the Orchestrator.

Specialists are read-only by default. A Specialist who becomes a Producer or
Builder must receive a separate write-capable assignment and then cannot provide
independent assurance for that result.

### Reviewer

The Reviewer independently evaluates a frozen artifact or implementation
against approved inputs, acceptance criteria, scope, quality standards, and
identified risks.

Responsibilities:

- remain read-only;
- report findings with severity, evidence, and required action;
- issue `APPROVE`, `SUPPLEMENT`, or `RECONSIDER`;
- distinguish blocking findings from recommendations;
- return the report to the Orchestrator.

The Reviewer does not repair the reviewed result and does not update the
canonical Work Block directly.

### Verifier

The Verifier independently reproduces the required checks against the reviewed
candidate and records observable evidence.

Responsibilities:

- remain read-only unless a separate documentation-only evidence path is
  explicitly approved;
- verify acceptance criteria, not implementation intent;
- report checks run, environment, evidence, limitations, and residual risks;
- issue `PASS` or `FAIL`;
- return the report to the Orchestrator.

The Verifier does not fix failures or reinterpret missing acceptance criteria as
success.

### Release Operator

The Release Operator performs an Owner-authorized release or deployment using
the approved Release Handoff.

Responsibilities:

- confirm the exact candidate, environment, authorization, prerequisites,
  backup or rollback plan, and monitoring path;
- execute only the approved release procedure;
- stop on candidate drift, missing approval, failed preflight, unexpected
  production state, or secret exposure;
- return release evidence and outcome.

The Release Operator does not decide that a candidate should be released unless
the same human is also the explicitly recorded Owner authority.

## Specialist labels

Recommended labels include:

- Product Analyst
- Architecture Analyst
- UX Analyst
- Design Analyst
- Frontend Analyst
- Backend Analyst
- Data Analyst
- Security Analyst
- QA Analyst
- Accessibility Analyst
- Content Analyst
- Operations Analyst
- Documentation Analyst

These labels specialize a core role; they do not create additional approval
authority.

## Separation of duties

| Activity | May produce | May independently review same result | May verify same result | May grant Owner approval |
| --- | --- | --- | --- | --- |
| Owner | Yes, when explicitly assigned | No | No | Yes |
| Orchestrator | Work Block and audit entries | No for its own subject output | No for its own subject output | No |
| Producer | Yes | No | No | No |
| Builder | Yes | No | No | No |
| Specialist | Analysis by default | Only if not a producer/contributor | Only if not a producer/contributor | No |
| Reviewer | No changes to reviewed result | Yes | Not for the same assurance step | No |
| Verifier | Evidence only | No | Yes | No |
| Release Operator | Release execution evidence | No | Preflight only, not independent candidate verification | No unless also recorded as human Owner |

For trivial work, a profile may make independent Review optional. It must never
represent self-checking as independent assurance.

## Subagent contract

Every delegated agent receives:

- role and specialization;
- objective and lifecycle stage;
- input artifacts and read scope;
- approved write-set, or an explicit read-only instruction;
- out of scope;
- expected Stage Result;
- checks, risks, stop conditions, and return deadline when relevant.

Subagents return structured results to the Orchestrator. They do not write the
canonical Work Block audit trail. Runtime logs are evidence only.

## Role transition rule

An actor may change roles only at a recorded step boundary. The Orchestrator
must state the new role, scope, permissions, and expected output. Previous
participation that compromises independence must be disclosed and a different
Reviewer or Verifier assigned.

