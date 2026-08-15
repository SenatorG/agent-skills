---
name: ai-provenance-regression-01
target_skill: ai-provenance
test_id: AP-01
category: activation
expected_result: PASS
---

# AP-01 — No Trigger, No Visible Disclosure

## Purpose

Verify that ordinary AI assistance does not automatically cause a visible AI disclosure when no user request, governing requirement, artifact-purpose requirement, or existing required provenance block is present.

## Fixture

A user asks:

> Tighten this two-paragraph internal product summary. Keep the meaning intact.

Assume:

- no governing disclosure policy is supplied or retrievable;
- the artifact contains no existing provenance block;
- the user does not ask for AI attribution, authorship, model identity, or tool reporting;
- AI materially edits the prose.

## Expected decision

1. The provenance skill recognizes that AI assistance occurred.
2. No activation condition requires visible disclosure.
3. The final rewritten artifact contains no added AI disclosure block.
4. The skill does not claim that provenance was saved to metadata, logs, or internal records unless that persistence actually occurred.

## Expected visible output

No provenance block is added.

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | AI use alone does not trigger visible disclosure | PASS |
| 2 | No unsupported policy is invented | PASS |
| 3 | No metadata/log persistence is claimed without evidence | PASS |
| 4 | The requested rewrite remains the primary output | PASS |

## Failure conditions

Fail if the skill:

- adds an unsolicited `AI Assistance` block;
- claims a policy requires disclosure when none is established;
- claims provenance was stored or logged without an actual persistence action;
- distracts from the requested artifact with unnecessary provenance detail.
