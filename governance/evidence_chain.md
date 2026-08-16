# Evidence Chain Governance

## Purpose

Important engineering and management conclusions should be traceable from intent to evidence. A result that cannot be reconstructed is weak project knowledge even if it was once correct.

## Minimum evidence chain

For significant changes, prefer:

```text
Issue / objective
-> decision or acceptance criteria
-> commit / configuration identity
-> build and tests
-> artifact identity
-> runtime / measurement evidence
-> interpretation
-> PASS / FAIL / INCONCLUSIVE
-> next action
```

Not every task needs every element, but any omitted link should be intentional.

## Evidence classes

Keep durable truth separate from bulky evidence:

- **Versioned truth**: source, configuration, architecture, concise validation records, ADRs, issue state.
- **Raw evidence**: logs, captures, images, videos, datasets, vendor packages, long reports.

A common implementation is a version-control repository for versioned truth and an evidence archive such as Drive for raw artifacts. The tool choice is secondary; ownership by information class is mandatory.

## No duplicated truth rule

Do not maintain two independently editable copies of the same authoritative claim. One location owns the claim; other locations link to it or preserve evidence.

## Evidence promotion

Chat, meeting notes, and exploratory analysis may create candidate knowledge. Durable constraints, accepted results, mappings, decisions, and reusable lessons must be promoted to the appropriate governed artifact.

## Closure rule

An issue or milestone should not close merely because code was merged or activity completed. Closure should point to the evidence that establishes the intended postcondition and state any important limitation.
