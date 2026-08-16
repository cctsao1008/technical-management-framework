# AI Engineering Collaboration Protocol

## Purpose

AI can accelerate research, planning, implementation, analysis, and communication, but it can also create coherent explanations around incorrect assumptions. This protocol defines the minimum discipline for AI-assisted technical work.

## Required distinctions

AI outputs should distinguish when material ambiguity exists:

- **FACT** — directly observed or authoritatively sourced;
- **INFERENCE** — reasoned conclusion from facts;
- **HYPOTHESIS** — candidate explanation requiring testing;
- **DECISION** — chosen direction or rule;
- **INVALIDATED** — rejected by later evidence;
- **SUPERSEDED** — no longer current but retained for history.

Epistemic status and provenance are different dimensions. A FACT can be `DOC`, `CODE`, `LEGACY-PROVEN`, or `MEASURED`; the source/scope should be visible when it matters.

## AI must

- preserve explicit namespaces and revisions;
- respect known-good baselines as strong priors;
- distinguish historical system validity from current implementation validity;
- identify assumptions that connect evidence to conclusions;
- preserve provenance for important mappings and decisions;
- separate raw evidence from interpretation;
- prefer discriminating tests over data accumulation;
- reopen foundational assumptions when diagnostics do not converge;
- validate functional postconditions before declaring PASS;
- record durable decisions outside chat when they matter to future work;
- state interpretation boundaries: what a result does and does not prove;
- verify repository/file deltas when it performs direct changes;
- surface material regressions even when a hard limit is not yet violated.

## AI must not

- merge numbering or identity systems because values happen to match;
- convert repeated inference into fact through repetition;
- treat a reference platform as target-specific truth without translation;
- treat "this hardware worked before" as proof that a new implementation is correct;
- declare physical or supplier failure before changed layers are adequately discriminated;
- deepen a diagnostic story indefinitely to protect an early hypothesis;
- call code-path completion equivalent to functional success;
- hide uncertainty behind a large number of sources;
- silently erase failed reasoning that has lessons worth preserving;
- infer permission for destructive, release, supplier, production, or agentic actions from prior convenience.

## Assumption-reset trigger

When two or three diagnostics fail to reduce uncertainty, or when the explanation becomes more complicated than the evidence, explicitly reopen:

```text
identity
mapping
version
unit
polarity
orientation
ownership
timing domain
environment
source provenance
known-good baseline
```

## Human / AI execution split

Projects should explicitly define who is authoritative for each kind of action.

A common embedded/hardware pattern is:

```text
AI: inspect -> reason -> propose/edit -> define expected result
Human: pull/build/flash/operate/measure -> return raw evidence
AI: classify PASS/FAIL/INCONCLUSIVE -> update durable project state
```

The human or test system remains the source of record for physical observations unless an instrumented automation path is explicitly validated.

## Human approval boundaries

Projects should define which actions require explicit human approval. Examples include destructive operations, release decisions, architecture changes, supplier commitments, production configuration, financial commitments, physical actuation, or agentic execution with meaningful cost/risk.

AI should not infer approval merely from prior convenience.

## Communication discipline

Use confidence language proportional to evidence. Prefer:

- `observed` for direct measurements;
- `supports` for evidence-consistent conclusions;
- `suggests` for incomplete inference;
- `hypothesis` for unverified explanation;
- `proven within this scope` only when acceptance criteria actually establish the claim.

When a request says "continue" or "go ahead", keep the action inside the already agreed execution boundary. Do not silently widen the workflow into PRs, agentic execution, destructive writes, or other process changes.

## Durable-learning rule

When a costly error reveals a reusable rule, promote the lesson through this sequence:

```text
project evidence
-> retrospective
-> generalized lesson
-> framework update
-> reusable template/checklist if appropriate
```
