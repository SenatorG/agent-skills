# Regression Test 07 — Iceberg Control and Safe Implication

## Objective

Verify that I2 can carry emotional meaning through action and juxtaposition in creative/editorial prose while leaving concrete facts intact and avoiding ambiguous business or safety implications.

## Test prompt

> Rewrite this as H3 / I2 Hemingway-inspired editorial prose. Use the iceberg principle. Do not imitate Hemingway's wording. Preserve the facts, but let the emotional meaning remain mostly unstated.
>
> "After eighteen months of work, the team presented the prototype to the customer. The customer tested it for twenty minutes, closed the laptop, and said, 'This solves the problem we described.' No one on the project team spoke for several seconds. The project lead then asked when the customer wanted to begin the production pilot."

## Expected behavior

The response may omit explicit explanations such as "the team felt relieved" or "the moment was emotional." The actions and silence should carry that meaning. But the factual sequence and quoted sentence must remain intact in substance.

## Pass criteria

- [ ] Preserves eighteen months of work.
- [ ] Preserves that the team presented the prototype to the customer.
- [ ] Preserves a twenty-minute customer test.
- [ ] Preserves the customer's statement: "This solves the problem we described," either verbatim or with no material change if quotation fidelity is required by the harness.
- [ ] Preserves several seconds of silence from the project team.
- [ ] Preserves that the project lead asks when to begin the production pilot.
- [ ] Does not explicitly explain the team's emotions unless needed for clarity.
- [ ] Lets action, silence, and juxtaposition carry much of the emotional meaning.
- [ ] Does not invent tears, smiles, weather, alcohol, war imagery, physical gestures, or internal thoughts.
- [ ] Does not turn the customer's statement into a production commitment or approval.

**Pass threshold: 10/10.**

## Critical failures

Automatic failure if the response:

- invents emotional or physical details;
- changes the customer statement into formal acceptance;
- implies that the production pilot was approved or scheduled;
- imitates recognizable Hemingway wording or creates obvious pastiche.

## Why this test matters

This is the one test where omission is a feature. The test passes only if implication increases while factual ambiguity does not.
