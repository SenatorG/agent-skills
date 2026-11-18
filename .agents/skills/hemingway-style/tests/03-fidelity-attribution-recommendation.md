# Regression Test 03 — Fidelity, Attribution, and Recommendation Strength

## Objective

Stress-test preservation of numbers, dates, product names, uncertainty, citations, attribution, limitations, customer actions, and the original strength of a recommendation.

## Test prompt

> Apply the Hemingway-style skill at H2 / I0. Rewrite the passage below for a customer-facing executive conversation. Preserve every material fact, qualifier, citation, limitation, attribution, and required action. Do not add facts or causal claims.
>
> The customer is currently considering the potential deployment of 12 Acme XE9680 servers during Q4 2026. The pricing provided is budgetary in nature and subject to change, and Acme has not made a commitment regarding the ship date. The customer has not yet completed validation of the power and cooling requirements within the data center, which must be addressed before the final configuration can be completed.
>
> The customer's HCI cluster averaged 38% CPU utilization and 81% storage utilization during the previous 90-day period.[1] The AI pilot also requires the ability to scale accelerator resources independently, although the amount of workload growth that may occur following Phase 1 is currently unknown. Given these factors, the architecture team recommends that the customer consider disaggregated infrastructure as one potential approach. However, the final decision depends on validation of data-center readiness and a better understanding of workload growth. The customer should confirm both items before the configuration is finalized.

## Expected behavior

The rewrite should be substantially cleaner while preserving every decision-relevant element. Attribution is part of fidelity: a team recommendation must not become an unattributed command or statement of fact.

## Pass criteria

- [ ] Preserves `12 Acme XE9680 servers` exactly in substance.
- [ ] Preserves `Q4 2026`.
- [ ] Preserves that pricing is budgetary and subject to change.
- [ ] Preserves that Acme has **not** committed to a ship date.
- [ ] Preserves that power and cooling validation is incomplete and required before final configuration.
- [ ] Preserves `38% CPU`, `81% storage`, and the `90-day` period.
- [ ] Keeps citation `[1]` attached to the utilization claim.
- [ ] Preserves the requirement to scale accelerator resources independently.
- [ ] Preserves that post-Phase-1 workload growth is unknown.
- [ ] Preserves attribution: **the architecture team** owns the recommendation.
- [ ] Preserves recommendation strength: `consider disaggregated infrastructure as one potential approach` does not become `use`, `choose`, `must adopt`, or equivalent.
- [ ] Preserves that the final decision depends on data-center readiness and better understanding of workload growth.
- [ ] Preserves the required customer action to confirm both before finalizing the configuration.
- [ ] Adds no unsupported causal relationship between HCI utilization and the recommendation.

**Pass threshold: 14/14.**

## Critical failures

Any missing number, date, product name, qualifier, citation, attribution, limitation, or required action is an automatic failure.

Also fail automatically if the output says or implies:

- Acme committed to Q4 shipment.
- HCI is wasting compute or storage based solely on the utilization figures.
- Disaggregated infrastructure is the required or only solution.

## Regression note

This test should remain in the suite even if the skill later adds an explicit attribution rule. Its job is to prevent that behavior from regressing.
