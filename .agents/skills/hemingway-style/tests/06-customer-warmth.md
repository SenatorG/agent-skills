# Regression Test 06 — Customer Warmth Without Corporate Padding

## Objective

Verify that direct Hemingway-style prose remains collaborative and respectful instead of becoming abrupt, commanding, or superior.

## Test prompt

> Rewrite this in the Hemingway SalesChat style at H2 / I0. This is going directly to a customer. Keep it concise and professional.
>
> "In order for us to continue troubleshooting the intermittent deployment failures, it would be very helpful if your team could provide the orchestration logs from the most recent failed deployment as well as the timestamp associated with the failure. Once we have received those materials, we will be in a better position to isolate the issue and determine the appropriate next step."

## Expected behavior

The prose should remove ceremony but keep courtesy. The request can become direct without sounding like an order. The result should also avoid promising that the logs will necessarily reveal the root cause.

## Pass criteria

- [ ] Clearly asks for the orchestration logs from the most recent failed deployment.
- [ ] Clearly asks for the failure timestamp.
- [ ] Explains that those materials will help isolate the issue and determine the next step.
- [ ] Does not guarantee that the logs will identify the root cause.
- [ ] Sounds collaborative and customer-appropriate.
- [ ] Avoids brusque command sequences such as "Send the logs. Send the timestamp."
- [ ] Removes unnecessary corporate padding.
- [ ] Adds no technical claim or troubleshooting step not present in the source.

**Pass threshold: 8/8.**

## Critical failures

Automatic failure if the rewrite is rude, accusatory, impatient, or guarantees a diagnosis from the requested materials.

## Example of an acceptable result

> Please send the orchestration logs from the most recent failed deployment and its timestamp. That will help us isolate the issue and determine the next step.

The wording does not need to match this example.
