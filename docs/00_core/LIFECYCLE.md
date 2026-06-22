# Canonical Web Delivery Lifecycle

## Purpose

This lifecycle defines the business process for taking a website or web
application from an initial request to a verified release handoff and subsequent
improvement. Profiles may combine adjacent stages or require additional
artifacts, but they must preserve stage intent, approval gates, and failure
routes.

## Operating principles

1. Business intent is approved before solution design.
2. Architecture decisions precede implementation that depends on them.
3. UX approval and visual approval are distinct decisions.
4. Building, reviewing, verifying, and releasing are distinct responsibilities.
5. Every stage consumes an approved input and produces a named artifact or
   verifiable result.
6. The Orchestrator advances work only after the current gate passes.
7. A failed gate returns work to the earliest stage capable of resolving the
   cause; it does not silently patch the symptom downstream.
8. Release authority remains with the Owner or an explicitly delegated human.

## Stages

| ID | Stage | Purpose | Required input | Required output | Exit gate | Failure route |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | Intake | Turn an initial request into a bounded discovery assignment | Owner request or opportunity | Project Intake | Owner confirms the problem is worth defining | Remain in Intake or close as declined |
| 1 | Product Definition | Define users, value, scope, constraints, success, and acceptance | Approved Project Intake | Project Brief | Owner approves product intent and scope | Return to Intake |
| 2 | Solution Architecture | Decide technical approach and identify data, API, backend, auth, security, integration, operational, and compliance constraints | Approved Project Brief | Solution Brief | Architecture and risk owners approve dependent decisions | Return to Product Definition when requirements are wrong; otherwise revise Architecture |
| 3 | UX | Define information architecture, user flows, page or screen structure, content needs, states, and interaction behavior | Approved Project Brief and Solution Brief | UX Specification | Product Owner approves usability direction and coverage | Revise UX; return to Product Definition or Architecture if the defect originates there |
| 4 | UI Design | Define visual direction, design system, responsive behavior, assets, and approved interface reference | Approved UX Specification | Design Specification and Design Review decision | Owner grants visual approval | Revise UI; return to UX when interaction structure is wrong |
| 5 | Implementation Planning | Convert approved specifications into ordered, bounded implementation Work Blocks | Approved product, architecture, UX, and design artifacts | Implementation Plan and ready Work Blocks | Orchestrator confirms Definition of Ready | Return to the artifact with missing or conflicting information |
| 6 | Build | Produce design assets, frontend, backend, integrations, content, or other approved deliverables | Ready Work Block and approved source artifacts | Implementation result and Stage Result | Builder checks pass and output is ready for independent review | Revise Build; escalate to Planning or earlier stage for scope or contract defects |
| 7 | Review | Evaluate correctness, quality, maintainability, scope compliance, and design fidelity without modifying the result | Build output and Stage Result | Review Report with verdict | Verdict is Approve, or all required supplements are resolved | Supplement returns to Build; Reconsider returns to the responsible earlier stage |
| 8 | Verification | Reproduce acceptance checks against the reviewed integrated result | Approved Review Report and candidate result | Verification Report with evidence | Verdict is Pass | Fail returns to Build or to the earliest defective specification stage |
| 9 | Release Handoff | Present a release-ready package, operational prerequisites, rollback information, and unresolved risks for human decision | Passed Verification Report | Release Handoff and Owner decision | Owner authorizes release or accepts handoff | Hold, return to Build, or reopen the responsible stage |
| 10 | Improvement | Capture production feedback, measurements, incidents, and opportunities as governed new work | Released outcome or validated feedback | Improvement Record and prioritized Intake candidates | Owner accepts next priorities | Retain in backlog or close with rationale |

## Simplified and extended delivery

A simplified profile may combine documentation when risk and complexity are
low. For example, Project Intake may be a section inside Project Brief, and UX
and Design Specification may be one approved document. It may not remove the
underlying decisions or their approval evidence.

An extended profile may split a canonical artifact into specialized documents,
such as data model, API contract, threat model, content plan, or test strategy.
The Artifact Registry must identify which file is authoritative for each field.

## Parallel work

Work may proceed in parallel only after shared contracts are approved. Frontend,
backend, content, and asset Work Blocks may run concurrently when their inputs,
interfaces, ownership, and integration checks are explicit. Each Work Block has
one writer; integration is a separate bounded assignment.

## Definition of Ready

A stage is ready only when:

- required inputs exist and have the required approval status;
- objective and expected result are unambiguous;
- role, write-set, out of scope, acceptance criteria, approver, checks, risks,
  and stop conditions are recorded;
- unresolved decisions do not prevent safe execution.

## Definition of Done

A stage is done only when:

- its required output exists at the canonical path;
- acceptance criteria and checks have evidence;
- deviations and residual risks are explicit;
- the required reviewer, verifier, or Owner verdict has been recorded;
- the next permitted state and responsible owner are known.

