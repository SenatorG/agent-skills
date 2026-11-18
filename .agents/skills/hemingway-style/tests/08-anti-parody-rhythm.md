# Regression Test 08 — Anti-Parody, Rhythm, and Paragraph Movement

## Objective

Verify that a strong Hemingway request produces disciplined syntax and rhythm without parody, fake toughness, fragment spam, decorative minimalism, or repeated conclusions.

## Test prompt

> Give this a strong Hemingway-inspired treatment, but keep it appropriate for an internal strategy memo. Do not imitate Hemingway's wording.
>
> "The team had spent several quarters discussing whether the AI platform should be treated primarily as a collection of infrastructure components or as an operating model. The distinction became more important as the number of use cases increased because each new workload introduced additional requirements for data access, security, deployment, observability, and lifecycle management. The conclusion of the workshop was that the platform cannot be evaluated only in terms of servers, accelerators, storage, and networking. The operating model also has to be considered because it determines how those resources can be consumed, governed, and changed over time."

## Expected behavior

The result should have a strong treatment while remaining suitable for a strategy memo. It should build forward rather than repeat "the platform is more than infrastructure" several times.

## Pass criteria

- [ ] Preserves the core distinction between infrastructure components and operating model.
- [ ] Preserves that the issue grew in importance as use cases increased.
- [ ] Preserves the workload requirements: data access, security, deployment, observability, and lifecycle management.
- [ ] Preserves the infrastructure categories: servers, accelerators, storage, and networking.
- [ ] Preserves the operating-model functions: consumption, governance, and change over time.
- [ ] Uses active verbs and concrete nouns where possible.
- [ ] Shows deliberate sentence-length variation.
- [ ] Avoids a chain of fragments or uniformly tiny sentences.
- [ ] Avoids invented toughness, masculinity, stoicism, weather, alcohol, hunting, blood, war, or battlefield imagery.
- [ ] Avoids quotation-like pastiche or archaic diction.
- [ ] Each sentence or paragraph advances the argument rather than merely restating the prior conclusion.
- [ ] Stops after the point lands instead of adding a generic summary sentence.

**Pass threshold: 12/12.**

## Critical failures

Automatic failure for parody markers, invented imagery, or loss of any listed technical/business requirement.

## Common bad-output patterns this test should catch

> The servers were there. The GPUs were there. The work was hard. The team knew what it had to do.

or

> Infrastructure mattered. But operations mattered too. That was the truth. It had always been the truth.

Both sound styled. Neither preserves the source with enough precision.
