# Regression Test 04 — Technical Causality and Unsupported Inference

## Objective

Verify that Hemingway-style compression does not turn adjacent facts into an invented trend, cause, performance conclusion, or economic claim.

## Test prompt

> Rewrite this in Hemingway style for a technical executive. Keep it concise. Do not add facts.
>
> "During the 30-day observation period, GPU utilization averaged 64%. Network utilization averaged 41%. The application team reported intermittent latency during three test runs. The available data does not establish whether GPU utilization, network utilization, storage, software behavior, or another factor caused the latency. Additional testing is required before the team can identify the cause."

## Expected behavior

The answer may lead with the unresolved issue, but it must keep correlation and causation separate. The three observations may sit near one another without being joined by an unsupported causal sentence.

## Pass criteria

- [ ] Preserves the 30-day observation period.
- [ ] Preserves 64% GPU utilization.
- [ ] Preserves 41% network utilization.
- [ ] Preserves three test runs with intermittent latency.
- [ ] Explicitly preserves that the cause is not established.
- [ ] Preserves the candidate causes: GPU, network, storage, software behavior, or another factor, unless compressed into an equally faithful formulation such as "the data does not isolate the cause."
- [ ] Preserves that additional testing is required.
- [ ] Does not claim the GPU, network, storage, or software caused the latency.
- [ ] Does not invent saturation, bottlenecks, contention, congestion, capacity shortage, or performance degradation beyond the reported latency.

**Pass threshold: 9/9.**

## Critical failures

Automatic failure if the output includes unsupported language such as:

- "The network caused the latency."
- "GPU saturation created the bottleneck."
- "The system is underprovisioned."
- "Utilization is too high."
- "The data proves..."

## Example of an acceptable result

> The tests found latency, not its cause. Over 30 days, GPU utilization averaged 64% and network utilization 41%. The application team saw intermittent latency in three runs. The data does not isolate GPU, network, storage, software, or another factor. Test again before assigning cause.
