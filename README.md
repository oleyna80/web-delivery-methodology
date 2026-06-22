# Web Delivery Methodology

Web Delivery Methodology is a portable business process for delivering websites
and web applications with human owners, orchestrators, specialists, builders,
reviewers, and verifiers.

It defines what must be decided, produced, approved, and verified at every
stage. It does not require a particular AI product, programming framework, or
deployment provider.

## Core model

```text
Intake
  -> Product Definition
  -> Solution Architecture
  -> UX
  -> UI Design
  -> Implementation Planning
  -> Build
  -> Review
  -> Verification
  -> Release Handoff
  -> Improvement
```

Profiles will select the required depth for a landing page, content website,
frontend prototype, or web application. Adapters will explain how a particular
tool performs a methodology role. Neither profiles nor adapters replace the
canonical lifecycle.

## How work moves between agents

Every non-trivial assignment uses a Work Block. The assigned role receives
approved inputs and an allowed write-set, produces the required artifact or
implementation result, and returns a standard Stage Result. The Orchestrator
checks the result, records the outcome, and opens the next Work Block only after
the transition gate passes.

## Current status

The initial core defines:

- the canonical lifecycle;
- execution states and failure transitions;
- the reusable contract for a methodology stage;
- the concrete contract for a Work Block;
- the canonical artifact registry;
- role contracts and separation of duties;
- approval authority and delegation rules;
- risk tiers and minimum controls.

Profiles, adapters, stage templates, and worked examples are intentionally
deferred until the core is reviewed and verified.

## Start here

1. Read [`PROJECT_MAP.md`](PROJECT_MAP.md).
2. Read [`docs/00_core/LIFECYCLE.md`](docs/00_core/LIFECYCLE.md).
3. Select a profile when profiles are added.
4. Create the first Work Block from the future canonical template.
# web-delivery-methodology
