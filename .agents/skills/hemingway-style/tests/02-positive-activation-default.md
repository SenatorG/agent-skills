# Regression Test 02 — Positive Activation and Default Strength

## Objective

Verify that an explicit Hemingway request activates the skill and that business/executive prose defaults to a full but controlled treatment: strong compression and rhythm with explicit business meaning.

## Test prompt

> Rewrite this in the Hemingway SalesChat style. I want it customer-facing and executive-level.
>
> "At this point in time, the architecture team believes that the most important issue for the customer is not necessarily whether additional infrastructure can be purchased, but whether the current operating model will allow the organization to deploy new AI workloads with the speed, consistency, and governance that will be required as adoption increases."

## Expected behavior

The response should show a clear stylistic transformation consistent with H2 while keeping business meaning explicit as I0. It should lead with the actual issue, cut nominalizations and throat-clearing, use concrete nouns and active verbs, and stop when the point lands.

## Pass criteria

- [ ] The rewrite is materially more compressed than the source.
- [ ] The central contrast remains: the issue is not merely buying infrastructure; it is whether the operating model can support AI deployment requirements.
- [ ] Speed, consistency, and governance are all preserved.
- [ ] The relationship to increasing AI adoption is preserved.
- [ ] The prose remains explicit enough for an executive/customer decision; it does not rely on literary implication.
- [ ] Sentence rhythm varies without fragment spam.
- [ ] No new claim, metric, product, or causal assertion is introduced.

**Pass threshold: 7/7.**

## Critical failures

- Any of speed, consistency, or governance disappears.
- The rewrite implies that more infrastructure is unnecessary rather than saying the larger issue is the operating model.
- The model invents a business outcome, benchmark, cost, or product recommendation.

## Example of an acceptable result

> The question is not whether the customer can buy more infrastructure. It is whether the operating model can deploy AI workloads with the speed, consistency, and governance the business will need as adoption grows.

The wording does not need to match this example.
