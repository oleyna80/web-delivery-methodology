# Project Map

## Current authoritative files

- `README.md` — purpose, operating model, and entry point.
- `AGENTS.md` — repository maintenance and orchestration rules.
- `docs/00_core/LIFECYCLE.md` — canonical delivery stages and gates.
- `docs/00_core/STATE_MACHINE.md` — execution states, verdicts, and transitions.
- `docs/00_core/STAGE_CONTRACT.md` — required definition of every lifecycle stage.
- `docs/00_core/WORK_BLOCK_CONTRACT.md` — contract for one bounded assignment.
- `docs/00_core/ARTIFACT_REGISTRY.md` — artifact ownership and source-of-truth map.
- `docs/00_core/ROLE_CONTRACTS.md` — role authority and separation of duties.
- `docs/00_core/APPROVAL_MATRIX.md` — lifecycle gates and human decision authority.
- `docs/00_core/RISK_TIERING.md` — risk classification and minimum controls.
- `docs/plans/` — project-maintenance Work Blocks for this repository.

## Planned layers

- `docs/01_profiles/` — lifecycle depth for different delivery types.
- `docs/02_adapters/` — mappings for tools and execution environments.
- `docs/03_templates/` — canonical input, output, review, and handoff templates.
- `docs/04_examples/` — completed simplified and extended examples.

Planned paths are not authoritative until their creating Work Block is approved
and the files exist.

## Boundaries

This repository contains methodology and document templates. It does not contain
application implementation, agent global configuration, secrets, model routing,
or deployment credentials.
