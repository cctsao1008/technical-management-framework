# Source-of-Truth Governance

## Purpose

Every project should define where current truth lives for each information class. Chat history, meeting notes, source code, issue trackers, documents, and supplier messages serve different purposes and should not compete silently.

## Required ownership map

For each project, define the authoritative location for:

- requirements;
- architecture;
- hardware mapping / interface contract;
- software configuration;
- release identity;
- milestones and current status;
- risks and assumptions;
- validation evidence;
- ADRs / decisions;
- raw artifacts and captures.

## Rule

A source of truth must be:

- identifiable;
- versioned or revision-aware when change matters;
- discoverable from the project entry point;
- scoped to a defined information class;
- linked to evidence where appropriate.

## Chat and AI outputs

Conversation is a working medium, not the final source of truth for durable project knowledge. Important constraints, decisions, mappings, accepted results, and reusable lessons must be promoted into governed artifacts.

## Conflict resolution

When two project artifacts disagree, do not silently reconcile them. Identify the owner of each artifact, determine which is authoritative for that claim, and update or mark the stale artifact as superseded.

## Cross-project rule

Reusable methods belong in the Technical Management Framework. Project-specific facts remain in the project repository or evidence archive. General principles must not overwrite target-specific truth.
