# 🧭 Technical Management Framework

A reusable framework for technical planning, project governance, engineering execution, evidence-based decision making, knowledge management, and AI-assisted collaboration across projects.

This repository is deliberately **project-agnostic**. Project-specific truth remains in each project repository; this repository defines the reusable management and execution framework shared across projects.

## 🎯 Scope

The framework covers:

- strategy and project framing;
- milestone and roadmap planning;
- technical governance and decision records;
- engineering execution and validation;
- risk and assumption management;
- evidence and knowledge management;
- retrospectives and continuous improvement;
- AI-assisted technical collaboration.

## 🗂️ Structure

```text
principles/       Fundamental rules for evidence, identity, baselines and decisions
planning/         Project framing, baselines, rebaseline gates, milestones and risk planning
governance/       Source of truth, evidence chains, ADRs, change control and review rules
execution/        Diagnostics, change integrity, resource budgets, validation and test acceptance
knowledge/        Evidence management, project-local truth and retrospectives
ai-collaboration/ AI reasoning, provenance, assumption reset and approval boundaries
templates/        Reusable project, ADR, rebaseline, validation, postmortem and evidence templates
case-studies/     Real projects converted into reusable organizational learning
```

## 🔄 Core model

```text
Project intent
    -> framing and constraints
    -> baseline / rebaseline
    -> plan and milestones
    -> governed decisions
    -> execution and evidence
    -> validation
    -> retrospective
    -> reusable learning
```

## 🧩 Separation of responsibilities

### 🧰 This repository owns

- reusable principles;
- reusable processes;
- reusable templates;
- cross-project terminology;
- generalized lessons and case studies.

### 📍 Individual project repositories own

- current architecture;
- project-specific requirements;
- exact hardware/software configuration;
- current risks and milestones;
- source code and executable configuration;
- project evidence links;
- project ADRs and validation status.

A framework rule must not silently replace project-local truth. A project may specialize a framework rule when the reason is explicit and recorded.

## 🚦 Recommended starting points

1. [`principles/evidence_and_truth.md`](principles/evidence_and_truth.md)
2. [`principles/identity_and_namespace.md`](principles/identity_and_namespace.md)
3. [`planning/known_good_baseline.md`](planning/known_good_baseline.md)
4. [`planning/rebaseline_gate.md`](planning/rebaseline_gate.md)
5. [`governance/source_of_truth.md`](governance/source_of_truth.md)
6. [`governance/evidence_chain.md`](governance/evidence_chain.md)
7. [`execution/diagnostic_design.md`](execution/diagnostic_design.md)
8. [`execution/test_acceptance.md`](execution/test_acceptance.md)
9. [`execution/change_integrity.md`](execution/change_integrity.md)
10. [`execution/resource_budgets.md`](execution/resource_budgets.md)
11. [`ai-collaboration/protocol.md`](ai-collaboration/protocol.md)
12. [`templates/project_local_truth.md`](templates/project_local_truth.md)
13. [`templates/rebaseline_checklist.md`](templates/rebaseline_checklist.md)
14. [`templates/validation_record.md`](templates/validation_record.md)

## 🧪 Case studies

Case studies preserve expensive failures and difficult decisions without turning project-specific details into universal rules.

- Case Study 001: Pi86-RP2350 host-mapping failure and recovery — initial source project: `cctsao1008/pi86-rp2350`.
- Case Study 002: Inverted Pendulum — restarting a known embedded system with AI; source project: `cctsao1008/inverted-pendulum`.
