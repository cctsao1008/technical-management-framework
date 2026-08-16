# Known-Good Baseline Method

## Purpose

Migration, porting, refactoring, supplier replacement, platform change, and process change should begin from an explicit known-good baseline.

## Baseline record

Before changing the system, record:

- hardware / environment;
- software / firmware versions;
- toolchain and dependencies;
- configuration;
- expected observable behavior;
- validation evidence;
- date and responsible source.

## Delta table

Every migration should explicitly separate:

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

## Planning use

Use the delta table before estimating schedule. A change that appears small at the feature level may cross several interfaces, namespaces, timing domains, or ownership boundaries.

## Exit condition

A migration is not complete merely when the new system works once. Record which baseline behaviors have been reproduced, which intentionally changed, and which remain unverified.
