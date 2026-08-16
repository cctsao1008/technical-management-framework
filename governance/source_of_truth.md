# Source-of-Truth Governance

## Purpose

Every project should define where current truth lives for each information class. Chat history, meeting notes, source code, issue trackers, documents, supplier messages, evidence archives, and dashboards serve different purposes and should not compete silently.

## Required ownership map

For each project, define the authoritative location for:

- requirements;
- architecture;
- hardware mapping / interface contract;
- software configuration;
- release identity;
- milestones and current status;
- risks and assumptions;
- validation conclusions;
- ADRs / decisions;
- raw artifacts and captures.

## Rule

A source of truth must be:

- identifiable;
- versioned or revision-aware when change matters;
- discoverable from the project entry point;
- scoped to a defined information class;
- linked to evidence where appropriate.

## Truth versus evidence

Do not make one repository or tool own every artifact merely for convenience.

Separate:

- **governed/versioned truth** — current architecture, configuration, decisions, concise validation state, and evidence links;
- **raw evidence** — logs, measurements, captures, images, videos, datasets, supplier packages, and long-form reports.

A practical pattern is version control for governed truth and a Drive-like evidence archive for bulky/raw artifacts. This is a pattern, not a mandatory tool choice.

## No duplicated truth rule

Two tools may contain related information, but they should not contain independently editable authoritative copies of the same claim. One location owns the claim; the other links to it or preserves supporting evidence.

## Chat and AI outputs

Conversation is a working medium, not the final source of truth for durable project knowledge. Important constraints, decisions, mappings, accepted results, and reusable lessons must be promoted into governed artifacts.

## Conflict resolution

When two project artifacts disagree, do not silently reconcile them. Identify the owner of each artifact, determine which is authoritative for that claim, and update or mark the stale artifact as superseded.

## Evidence chain

For significant conclusions, preserve the chain from issue/objective through configuration or commit identity, validation evidence, interpretation, and result. See [`evidence_chain.md`](evidence_chain.md).

## Cross-project rule

Reusable methods belong in the Technical Management Framework. Project-specific facts remain in the project repository or evidence archive. General principles must not overwrite target-specific truth.
