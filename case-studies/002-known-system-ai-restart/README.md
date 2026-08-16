# Case Study 002 — Restarting a Known Embedded System with AI

## Why this case matters

A previously working embedded-control platform was restarted with a new software architecture and AI-assisted development workflow. The expensive difficulty was not a single control algorithm defect. The project initially treated a known physical system too much like a greenfield bring-up, while historical truth, current implementation truth, and AI inference were not separated rigorously enough.

This case is useful because the failure pattern applies to inherited products, rewrites, supplier transitions, platform migrations, lab prototypes, and any project where a working legacy system is rebuilt through a new implementation.

## Initial assumptions and framing

**FACT:** The physical platform had historical evidence of working behavior.

**FACT:** The new codebase still needed to validate its own mappings, scaling, timing, safety semantics, and integration.

**INFERENCE:** Because these two facts were not represented as separate status dimensions early enough, the project repeatedly rediscovered information and sometimes discussed known hardware as though it were an unknown greenfield target.

## What changed

The collaboration gradually introduced:

- explicit known-good baseline handling;
- provenance-aware truth tables;
- atomic issue/commit/test/runtime evidence chains;
- fail-closed control integration;
- dedicated runtime status rather than optional diagnostics as safety transport;
- explicit state-machine admission semantics;
- resource/performance regression tracking;
- human/AI execution boundaries;
- repository-delta verification for direct AI edits.

## Challenges and misleading evidence

### Historical validity versus current implementation validity

**FACT:** A historically valid subsystem did not automatically prove that a newly written driver or interpretation was correct.

**GENERALIZED LESSON:** Track legacy/system validity and current-implementation validity separately.

### Evidence provenance

**FACT:** Schematics, old code, current measurements, and inference can all support similar-looking claims while having different scope.

**GENERALIZED LESSON:** Epistemic status and provenance are orthogonal. A project needs both when ambiguity is costly.

### Safety-state transport

**SUPERSEDED:** An optional diagnostic/trace path was initially used to carry information needed by a closed-loop gate.

**DECISION:** Safety-relevant decisions should consume dedicated runtime status and fail closed when status is unavailable or stale.

### Incomplete state-transition semantics

**SUPERSEDED:** The gate existed before a complete legitimate admission path was defined.

**DECISION:** Define the state graph and admission/run semantics before binding physical actuation.

### Hidden resource regression

**FACT:** A functionally valid change produced a material control-path timing regression while remaining inside the absolute real-time deadline.

**GENERALIZED LESSON:** Resource regressions deserve attribution even before a hard limit is exceeded.

### AI repository-write hazards

**FACT:** Direct AI-assisted repository work produced avoidable process noise, including accidental whole-file replacement risk, temporary/no-op commits, and leftover candidate branches.

**DECISION:** Large or safety-critical file changes require exact-baseline fetch, candidate-diff verification, expected changed-file counts, and fast-forward-only acceptance.

## Root cause model

```text
legacy knowledge not represented as structured evidence
+ historical validity conflated with current implementation validity
+ chat used as temporary project memory
+ greenfield framing applied to a reused system
+ insufficiently explicit tool/workflow boundaries
=
rediscovery, assumption drift, misleading diagnostics, and avoidable repository churn
```

## Corrective action pattern

```text
Gate 0: rebaseline
    -> truth/provenance/assumption records
Gate 1: observe-only integration
    -> no automatic actuation
Gate 2: admission and safety semantics
    -> dedicated status, fail closed
Gate 3: controlled actuation
    -> explicit authority and limits
Gate 4: plant/controller commissioning
    -> measured envelopes and performance budgets
```

This sequence is illustrative; projects should adapt gate names and count to their risk profile.

## Framework changes caused by this case

- add a formal Rebaseline Gate;
- extend known-good baseline handling with two-axis legacy/current validation;
- distinguish provenance from epistemic status;
- add evidence-chain governance;
- add repository change-integrity rules for AI/automation;
- add engineering resource budgets;
- extend project-local truth and validation templates;
- clarify human/AI execution and approval boundaries.

## Risk of over-generalization

Not every project needs a formal Gate 0 or detailed provenance table. Small greenfield software-only work may use a lighter process. The method becomes valuable when legacy evidence, hardware, suppliers, safety, real-time constraints, or multiple sources of truth create meaningful ambiguity or consequence.

## Source project

Project-specific hardware mappings, measurements, firmware parameters, issue IDs, exact commits, and raw logs remain in the source project's repository/evidence archive. This case deliberately retains only the reusable lessons.
