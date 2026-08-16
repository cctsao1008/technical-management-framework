# Identity and Namespace Discipline

## Rule

Identifiers are meaningful only inside an explicit namespace.

Examples:

- physical pin vs BCM GPIO vs MCU GPIO;
- marketing version vs release tag vs commit SHA vs binary hash;
- logical device ID vs physical device identity;
- virtual address vs physical address;
- Jira issue number vs firmware build identifier;
- supplier part name vs silicon revision.

Never merge identifiers merely because their numeric or textual values happen to match.

## Required representation

For every cross-system mapping, document the chain explicitly:

```text
source namespace
    -> stable interface / identity
    -> target namespace
```

Prefer a stable physical, protocol, schema, or contractual identity as the bridge.

## Review rule

Before diagnosing behavior, first prove identity.

```text
identity
-> ownership / direction
-> state
-> timing
-> protocol meaning
-> root-cause interpretation
```

## Anti-patterns

Avoid naked identifiers such as `GPIO9`, `v1.4`, `node 3`, or `build latest` when more than one namespace or revision system exists.

Use forms such as:

```text
RP2350 GPIO9
RPi physical pin 32
release tag e61-v1.4
commit <sha>
binary SHA256 <hash>
```

## Management consequence

Namespace ambiguity is not only a technical defect. It can corrupt status reporting, supplier communication, validation scope, release tracking, and schedule decisions. Identity contracts belong in project governance, not only in source code.
