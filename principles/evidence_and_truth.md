# Evidence and Truth Hierarchy

## Purpose

Technical management fails when observations, documents, assumptions, and decisions are flattened into one narrative. This document defines how claims are ranked and labeled across projects.

## Default evidence priority

1. Verified behavior of the actual system under test.
2. Current target-specific official documentation, schematic, API contract, datasheet, or authoritative specification.
3. Project-owned source-of-truth documents and executable configuration.
4. Current upstream/reference implementation.
5. Historical artifacts and archived revisions.
6. Derived interpretation.
7. Unverified hypothesis.

A lower-priority source must not silently override higher-priority evidence.

## Required epistemic labels

Use these labels when ambiguity matters:

- **FACT** — directly observed or directly supported by an authoritative source.
- **INFERENCE** — derived from facts but not directly observed.
- **HYPOTHESIS** — candidate explanation requiring discrimination.
- **DECISION** — chosen action, rule, architecture, or management direction.
- **INVALIDATED** — previously plausible interpretation rejected by later evidence.
- **SUPERSEDED** — historically valid or previously used material that is no longer current.

## Provenance is a separate dimension

Epistemic status answers "what kind of claim is this?" Provenance answers "where did it come from and in what scope?"

Useful provenance labels include:

- `MEASURED` — observed on the current target/specimen/environment;
- `LEGACY-PROVEN` — demonstrated by a previous known-good system;
- `DOC` — supported by authoritative documentation;
- `CODE` — encoded by an implementation or executable configuration;
- `INFERRED` — derived from other evidence;
- `UNKNOWN` — unresolved source/validity.

Examples:

```text
FACT + DOC
FACT + MEASURED
FACT + LEGACY-PROVEN
INFERENCE + DOC/CODE inputs
HYPOTHESIS + UNKNOWN target behavior
```

Do not silently promote `INFERRED` or `LEGACY-PROVEN` into `MEASURED` current-target truth.

## Scope rule

Every important claim should have enough scope to prevent accidental overreach:

```text
target / specimen / environment / revision / mode / time
```

A true claim outside the current scope can still be the wrong basis for a decision.

## Conflict handling

When sources conflict:

1. identify the exact conflicting claim;
2. identify the source, target, revision, timestamp, and scope of each claim;
3. check whether the conflict is actually a version, namespace, environment, or operating-mode difference;
4. prefer target-specific and experimentally verified evidence;
5. record the resolution;
6. explicitly mark the displaced interpretation as invalidated or superseded.

## Evidence independence

Do not increase confidence merely because many documents repeat the same intermediate assumption. Ten documents copied from one incorrect mapping are not ten independent confirmations.

## Management consequence

Plans, schedules, escalations, and resource decisions should identify which assumptions are strongly evidenced and which remain uncertain. Uncertainty should be visible before it becomes schedule risk.
