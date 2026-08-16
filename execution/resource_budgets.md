# Engineering Resource Budgets

## Purpose

A system may remain functional while consuming materially more timing, memory, bandwidth, power, thermal headroom, or operational margin. Projects should define resource budgets before those margins become commissioning surprises.

## Budget classes

Use only the classes relevant to the project, for example:

- real-time execution time / deadline margin;
- CPU load;
- ROM / RAM;
- bus or network bandwidth;
- queue depth / latency;
- power / current;
- thermal margin;
- storage;
- reliability/error-rate budget;
- safety-state response time.

## Baseline and thresholds

For each important budget, record:

```text
baseline
normal target
warning threshold
hard limit / deadline
measurement method
scope / mode
```

## Regression rule

A change can be functionally PASS and still create a material regression. Significant resource changes require attribution or explicit acceptance before riskier milestones.

Avoid using only absolute limits. A change from 20% to 30% CPU may be worth investigation even when the hard deadline is still far away.

## Gate rule

Before active commissioning, production release, or other high-consequence gates, unresolved resource regressions must be either:

- understood and accepted;
- mitigated; or
- explicitly tracked with rationale for proceeding.

## Management consequence

Budgets turn hidden technical margin into visible project risk. They also prevent performance work from becoming premature optimization: optimize when evidence shows a budget problem or meaningful regression.
