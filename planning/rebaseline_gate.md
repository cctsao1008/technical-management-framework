# Rebaseline Gate

## Purpose

Projects that restart, inherit, migrate, refactor, or replace a previously working system must not begin by treating the system as greenfield. Before feature development, establish what is already known, what changed, and what still requires revalidation.

## Gate entry conditions

Use this gate when any of the following apply:

- reused hardware or software;
- platform or supplier migration;
- project restart after a gap;
- legacy system recovery;
- new implementation on a known physical system;
- major refactor where historical behavior matters.

## Required outputs

Before the gate can close, record:

1. **System identity** — hardware revision, software baseline, environment, specimen, and release identity.
2. **Known-good behavior** — what the legacy/current system demonstrably did.
3. **Truth table** — important interfaces, mappings, units, polarity/orientation, ownership, source, and validation state.
4. **Delta table** — what is unchanged versus changed.
5. **Assumption register** — unresolved claims with impact and verification action.
6. **Source-of-truth map** — where current truth and raw evidence live.
7. **Baseline evidence** — reproducible build/test/runtime records where available.
8. **Initial budgets** — timing, memory, safety, reliability, or other constraints that can regress silently.

## Two-axis validation rule

Never flatten these into one status:

```text
legacy/system-level validity
current implementation validity
```

A subsystem may be historically proven while its new driver, mapping, scaling, or integration remains unverified.

## Exit criteria

The gate closes when:

- legacy-proven facts are explicitly distinguished from newly measured facts;
- important assumptions have owners or verification actions;
- changed layers are visible;
- project-specific truth is discoverable from a durable project entry point;
- no critical implementation decision depends on an undocumented identity/mapping/version assumption.

## Management consequence

Schedule and architecture estimates made before rebaseline completion should be treated as provisional. The gate exists to reduce rediscovery, assumption drift, and debugging of unchanged layers.
