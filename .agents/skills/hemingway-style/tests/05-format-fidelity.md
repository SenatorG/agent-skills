# Regression Test 05 — Format, Terminology, and Scanability

## Objective

Verify that the skill does not convert scan-oriented technical content into literary prose when bullets are the better operational format.

## Test prompt

> Apply the Hemingway style at H2 / I0. Tighten this for a customer architecture review. Keep the bullet format.
>
> - **Compute:** 8 Acme R760xa servers are proposed. Final quantity is subject to sizing validation.
> - **Accelerators:** Each proposed server includes 4 NVIDIA L40S GPUs. GPU selection may change after application testing.
> - **Network:** The design assumes 100 GbE connectivity. Switch port availability has not yet been confirmed.
> - **Storage:** Capacity is estimated at 240 TB usable. The estimate excludes backup retention.
> - **Next action:** The customer must confirm rack power, available switch ports, and backup-retention requirements before the BOM is finalized.

## Expected behavior

The output should remain a bullet list with the same five categories. It may tighten phrases but should not flatten qualifiers or turn the content into connected prose.

## Pass criteria

- [ ] Keeps bullet format.
- [ ] Keeps all five categories: Compute, Accelerators, Network, Storage, Next action.
- [ ] Preserves `8 Acme R760xa`.
- [ ] Preserves `4 NVIDIA L40S GPUs` per proposed server.
- [ ] Preserves `100 GbE`.
- [ ] Preserves `240 TB usable`.
- [ ] Preserves that compute quantity is subject to sizing validation.
- [ ] Preserves that GPU selection may change after application testing.
- [ ] Preserves that switch port availability is unconfirmed.
- [ ] Preserves that storage excludes backup retention.
- [ ] Preserves all three required confirmations before BOM finalization: rack power, switch ports, backup retention.
- [ ] Does not rename products or technical terms inaccurately.

**Pass threshold: 12/12.**

## Critical failures

Automatic failure if the response:

- converts the list into prose despite the explicit instruction;
- drops a qualifier;
- changes a quantity or technical term;
- turns an assumption into a confirmed fact;
- removes any required next action.
