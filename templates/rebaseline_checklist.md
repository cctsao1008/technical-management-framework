# Rebaseline Checklist

Use before major development on a restarted, inherited, migrated, refactored, or known-good system.

## Identity

- [ ] Hardware / system revision identified
- [ ] Specimen / environment identified
- [ ] Software / firmware baseline identified
- [ ] Toolchain and critical dependency versions identified
- [ ] Release / commit / binary identity recorded where applicable

## Known-good behavior

- [ ] Historical validated behavior listed
- [ ] Evidence or responsible source linked
- [ ] Meaning of "validated" stated per subsystem
- [ ] Legacy-proven behavior separated from current-implementation validation

## Truth and provenance

- [ ] Critical interface truth table exists
- [ ] Mapping / units / polarity / orientation / ownership recorded
- [ ] Important claims include source/provenance
- [ ] Stale or conflicting artifacts marked SUPERSEDED / INVALIDATED where appropriate

## Delta

- [ ] UNCHANGED layers listed
- [ ] CHANGED layers listed
- [ ] Debugging priority follows the change set unless evidence says otherwise

## Assumptions and risk

- [ ] Assumption register exists
- [ ] High-impact assumptions have verification actions
- [ ] Safety-critical unknowns are fail-closed where practical
- [ ] Initial timing/memory/safety/reliability budgets defined where relevant

## Governance

- [ ] Source-of-truth ownership map defined
- [ ] Chat/meeting notes are not the sole durable record for critical facts
- [ ] Raw evidence archive location defined
- [ ] Human approval boundaries defined

## Validation

- [ ] Reproducible build/test baseline captured
- [ ] Acceptance criteria verify postconditions, not activity completion
- [ ] Artifact identity and runtime/measurement evidence can be linked

## Gate decision

- [ ] PASS — sufficient baseline recovered to proceed
- [ ] CONDITIONAL — proceed only with explicit tracked gaps
- [ ] FAIL — development should remain in rebaseline/recovery

Open gaps / rationale:
