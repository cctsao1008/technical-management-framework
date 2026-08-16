# Known-Good Baseline Method

## Purpose

Migration, porting, refactoring, supplier replacement, platform change, restart, and process change should begin from an explicit known-good baseline.

A known-good baseline is not only a software version. It is a bounded claim about a specific system, environment, configuration, and observable behavior.

## Baseline record

Before changing the system, record:

- hardware / environment;
- software / firmware versions;
- toolchain and dependencies;
- configuration;
- expected observable behavior;
- validation evidence;
- date and responsible source.

## Separate historical validity from current implementation validity

Do not compress these into a single PASS/FAIL field:

```text
legacy/system behavior was validated
current implementation of that interface is validated
```

A reused subsystem can be **LEGACY-PROVEN** while a new driver, mapping, scaling, timing path, or integration remains unverified.

Recommended provenance vocabulary when useful:

- `LEGACY-PROVEN` — demonstrated by the prior known-good system;
- `DOC` — supported by authoritative documentation;
- `CODE` — encoded by a prior/current implementation;
- `MEASURED` — directly observed on the current target/specimen;
- `INFERRED` — derived but not directly verified;
- `UNKNOWN` — unresolved.

These provenance tags complement, rather than replace, the framework's epistemic labels such as FACT, INFERENCE, and HYPOTHESIS.

## Delta table

Every migration or restart should explicitly separate:

```text
UNCHANGED
- components
- interfaces
- requirements
- validated behavior

CHANGED
- platform
- implementation
- mapping
- toolchain
- supplier
- timing
- configuration
```

Debugging priority should initially follow the change set.

## Strong-prior rule

A component that demonstrably works in the known-good baseline should not be casually reclassified as defective in the new system without new discriminating evidence.

The baseline does not prove compatibility with the new environment; it constrains the root-cause search space.

## Rebaseline rule

If the prior baseline exists only as human memory, scattered chat, stale documentation, or an unavailable build, first perform a rebaseline/recovery activity. Recover enough identity, expected behavior, provenance, and evidence to distinguish what is being reused from what is actually being redesigned.

See [`rebaseline_gate.md`](rebaseline_gate.md).

## Planning use

Use the delta table before estimating schedule. A change that appears small at the feature level may cross several interfaces, namespaces, timing domains, or ownership boundaries.

## Exit condition

A migration is not complete merely when the new system works once. Record which baseline behaviors have been reproduced, which intentionally changed, and which remain unverified.
