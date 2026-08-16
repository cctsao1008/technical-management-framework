# Case Study 001 — Pi86 RP2350 Host-Mapping Failure

## Why this case matters

A known-good Pi86 V20/V30 HAT and physical NEC V30 CPU were migrated from a Raspberry Pi host to a Waveshare RP2350-PiZero host. The new implementation initially produced contradictory bus diagnostics despite the same HAT/CPU assembly being known-good on the original platform.

The expensive failure was not caused by the CPU, HAT, or a subtle electrical defect. The primary failure was an identity/translation error across GPIO numbering domains.

## Core failure pattern

```text
validated system
    -> platform migration
    -> reference-platform identifiers copied into target-platform context
    -> signal identity becomes wrong
    -> diagnostics accurately measure the wrong signals
    -> increasingly detailed but incorrect technical narrative
    -> foundational assumption reset
    -> mapping corrected through physical connector identity
    -> expected behavior restored
```

## Root cause

Raspberry Pi WiringPi/BCM numbering was conflated with RP2350 GPIO numbering. The stable interface was the physical Raspberry Pi 40-pin header, but the migration initially skipped the explicit physical-pin-to-target-GPIO translation step.

The generalized rule is:

```text
logical/reference namespace
    != physical interface identity
    != target namespace
```

## Contributing factors

- The same numeric GPIO values happened to match at several physical positions, creating false confidence.
- Multiple upstream/reference documents repeated the reference-platform mapping, increasing evidence density without adding independent target-platform evidence.
- The known-good HAT/CPU baseline was not weighted strongly enough when hardware-fault hypotheses emerged.
- Diagnostics became progressively more detailed before the signal identities were independently revalidated.
- Some early PASS criteria verified code-path completion rather than the intended functional postcondition.
- CPU instruction semantics were initially equated too directly with external bus transaction order, ignoring prefetch behavior.

## Model-reset moment

The decisive step was returning to the target board's physical header pinout and re-establishing the translation chain:

```text
V30 signal
-> Raspberry Pi physical header pin
-> RP2350-PiZero routing
-> RP2350 GPIO
```

Once corrected, reset-vector fetch, aligned memory reads, real ROM execution, RAM write/readback, compare, and conditional branch behavior became deterministic.

## Generalized lessons promoted into this framework

1. Physical/protocol identity should bridge namespace translations.
2. Verify signal identity before interpreting signal behavior.
3. Preserve known-good baselines as strong debugging priors.
4. Evidence density is not evidence independence.
5. After non-converging diagnostics, reopen foundational assumptions.
6. PASS criteria must validate functional postconditions.
7. Do not collapse behavior across abstraction layers such as instruction semantics and external bus transactions.
8. Important conversational constraints and discoveries must be promoted into governed artifacts.

## Source project

Authoritative project-specific details, exact mappings, commits, and hardware evidence remain in:

- `cctsao1008/pi86-rp2350`
- project hardware contract and pin-mapping documents;
- bring-up Gates 3–6 evidence;
- Gate 4 debugging issue / retrospective.

This case study intentionally preserves only the reusable management and engineering lessons. Project-specific truth remains owned by the source project.
