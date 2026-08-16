# Change Integrity and Repository Write Safety

## Purpose

Repository automation and AI-assisted edits can introduce failures unrelated to the intended engineering change. Change integrity is therefore part of validation, not clerical cleanup.

## Atomic-change rule

One commit should have one clear engineering objective whenever practical. Unrelated cleanup, temporary files, markers, or speculative edits should not ride with a functional change.

## Baseline rule

Before a write:

1. read the latest target branch;
2. identify the exact files and expected delta;
3. abort/rebase if the baseline moved;
4. never force-update normal development history merely to simplify tooling.

## Large-file rule

Whole-file replacement is high risk for large or safety-critical files.

For such files:

1. fetch the exact complete current content;
2. build the candidate from that exact baseline;
3. verify the candidate file and the base-to-candidate diff;
4. check changed-file count and additions/deletions against expectation;
5. reject unexpected deletions or unrelated changes;
6. fast-forward only after the diff is understood.

Prefer tree/blob or patch-based workflows when they make the intended delta easier to prove than ad-hoc contents replacement.

## Candidate-branch rule

Temporary candidate branches are an implementation detail unless the project explicitly uses PR review. They should not silently alter the user's expected workflow or create misleading PR prompts.

## Failure preservation

If tooling produces accidental commits or transient repository noise, do not hide the incident by rewriting shared history without explicit reason. Correct the tree, preserve the audit trail when useful, and record a reusable lesson when the failure exposes a process hazard.

## Acceptance

A repository change is accepted only after both are true:

- engineering behavior meets its acceptance criteria;
- repository delta matches the intended scope.
