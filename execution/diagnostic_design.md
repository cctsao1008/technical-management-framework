# Diagnostic Design Discipline

## Objective

A diagnostic should discriminate between competing explanations, not merely generate more data.

## Standard issue structure

```text
Observed evidence
Candidate hypotheses
Assumptions
Next discriminating test
Result
Interpretation
Invalidated / surviving hypotheses
```

## Model-reset trigger

Stop increasing diagnostic depth and reopen foundational assumptions when any of these occur:

- two or three consecutive diagnostics fail to reduce uncertainty;
- new results contradict the current model;
- increasingly complex explanations are required to preserve the current story;
- a test depends on an identity, mapping, version, polarity, unit, or ownership assumption that has not been independently verified.

Recheck:

```text
identity
mapping
version / revision
orientation
units
polarity
clock / timing domain
environment
source provenance
known-good baseline
```

## Minimum-difference principle

When comparing a working system and failing system, first isolate what changed. Prefer tests that distinguish changed layers before reopening unchanged layers.

## Diagnostic debt

Temporary diagnostics are useful, but they create debt when their assumptions become invalid. If a foundational assumption changes, mark affected evidence as superseded and identify which tests require rerun.

## Management consequence

Diagnostic depth consumes schedule and attention. A technical lead should periodically ask whether the team is learning about the real system or merely refining an unverified model.
