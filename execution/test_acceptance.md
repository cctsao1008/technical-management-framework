# Test Acceptance Discipline

## Rule

A test passes only when its intended functional postconditions are verified.

Do not confuse:

- program completed;
- code path executed;
- signal toggled;
- transaction occurred;
- expected result was actually produced.

## Acceptance definition

Before implementing a test, write:

```text
Capability under test
Preconditions
Stimulus
Expected observable result
Failure conditions
Evidence to retain
Interpretation boundary
```

## Postcondition rule

A PASS condition must compare the actual result against the required result whenever that comparison is technically possible.

Examples:

- requested data must equal observed data;
- written value must be read back by the consumer, not merely inspected by the producer;
- a branch test should verify the selected path;
- a communication test should verify payload semantics, not just transport completion.

## Layer rule

Do not equate behavior at different abstraction layers. CPU instruction semantics, bus transactions, protocol frames, driver calls, and application outcomes may differ because of buffering, prefetch, caching, retries, pipelines, or scheduling.

## Evidence retention

For each important gate, retain:

- test target / procedure;
- source or commit identifier;
- exact output;
- raw measurement or capture when applicable;
- PASS/FAIL interpretation;
- limitations not established by the test.

## Management consequence

Milestone completion must be tied to validated capability, not activity completion. A green test that validates the wrong condition is a project risk, not progress.
