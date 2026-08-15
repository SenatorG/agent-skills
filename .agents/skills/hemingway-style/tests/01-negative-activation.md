# Regression Test 01 — Negative Activation

## Objective

Verify that ordinary requests for concise, direct, short, or less-corporate prose do **not** activate the Hemingway SalesChat skill unless the user explicitly invokes Hemingway, the iceberg principle/style, or the skill itself.

## Test prompt

> Rewrite this to be shorter, more direct, and less corporate. Use short sentences and cut the fat.
>
> "In light of the fact that the project team has reached the conclusion that there are a number of unresolved dependencies that may potentially affect the timeline, we believe it would be prudent to conduct an additional review before proceeding with the implementation phase."

## Expected behavior

The model should perform a normal concise rewrite. It may use strong verbs and shorter sentences because the user requested them, but it must **not** announce, label, or deliberately apply Hemingway/iceberg treatment.

## Pass criteria

Score 1 point for each:

- [ ] Does not mention Hemingway, iceberg, H1/H2/H3, or I0/I1/I2.
- [ ] Does not claim to be applying the Hemingway SalesChat skill.
- [ ] Preserves the core meaning: unresolved dependencies may affect the timeline and an additional review is recommended before implementation.
- [ ] Preserves uncertainty; does not turn "may potentially affect" into a definite schedule impact.
- [ ] Produces concise professional prose without theatrical or literary styling.

**Pass threshold: 5/5.**

## Critical failures

Any of the following is an automatic failure:

- The response explicitly says it is using Hemingway or iceberg style.
- The rewrite changes uncertainty into certainty.
- The rewrite removes the recommendation to review before implementation.

## Example of an acceptable result

> The project still has unresolved dependencies that may affect the timeline. Review them before implementation begins.

The wording does not need to match this example.
