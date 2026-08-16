# Technical Management Framework

A reusable framework for technical planning, project governance, engineering execution, evidence-based decision making, knowledge management, and AI-assisted collaboration across projects.

This repository is deliberately **project-agnostic**. Project-specific truth remains in each project repository; this repository defines the reusable management and execution framework shared across projects.

## Scope

The framework covers:

- strategy and project framing;
- milestone and roadmap planning;
- technical governance and decision records;
- engineering execution and validation;
- risk and assumption management;
- evidence and knowledge management;
- retrospectives and continuous improvement;
- AI-assisted technical collaboration.

## Structure

```text
principles/       Fundamental rules for evidence, identity, baselines and decisions
planning/         Project framing, milestones, prioritization and risk planning
governance/       Source of truth, ADRs, change control and review rules
execution/        Diagnostics, migration/porting, validation and test acceptance
knowledge/        Evidence management, project-local truth and retrospectives
ai-collaboration/ AI reasoning, provenance, assumption reset and approval boundaries
templates/        Reusable project, ADR, postmortem and evidence templates
case-studies/     Real projects converted into reusable organizational learning
```

## Core model

```text
Project intent
    -> framing and constraints
    -> plan and milestones
    -> governed decisions
    -> execution and evidence
    -> validation
    -> retrospective
    -> reusable learning
```

## Separation of responsibilities

### This repository owns

- reusable principles;
- reusable processes;
- reusable templates;
- cross-project terminology;
- generalized lessons and case studies.

### Individual project repositories own

- current architecture;
- project-specific requirements;
- exact hardware/software configuration;
- current risks and milestones;
- source code and executable configuration;
- project evidence links;
- project ADRs and validation status.

A framework rule must not silently replace project-local truth. A project may specialize a framework rule when the reason is explicit and recorded.

## Recommended starting points

1. [`principles/evidence_and_truth.md`](principles/evidence_and_truth.md)
2. [`principles/identity_and_namespace.md`](principles/identity_and_namespace.md)
3. [`planning/known_good_baseline.md`](planning/known_good_baseline.md)
4. [`execution/diagnostic_design.md`](execution/diagnostic_design.md)
5. [`execution/test_acceptance.md`](execution/test_acceptance.md)
6. [`ai-collaboration/protocol.md`](ai-collaboration/protocol.md)
7. [`templates/project_local_truth.md`](templates/project_local_truth.md)

## Case studies

Case studies preserve expensive failures and difficult decisions without turning project-specific details into universal rules.

- Case Study 001: Pi86-RP2350 host-mapping failure and recovery — initial source project: `cctsao1008/pi86-rp2350`.

## Status

Initial framework extracted from lessons learned during cross-platform firmware, hardware bring-up, migration, project governance, and AI-assisted engineering work. The framework is expected to evolve as additional projects contribute validated lessons.
