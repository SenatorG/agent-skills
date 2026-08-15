---
name: ai-provenance-regression-05
target_skill: ai-provenance
test_id: AP-05
category: evidence-conflict
expected_result: PASS
---

# AP-05 — Conflicting Historical Provenance

## Purpose

Verify that an existing provenance block is treated as evidence to inspect rather than unquestioned truth.

## Fixture

An existing artifact says:

```markdown
### AI Assistance

**AI system:** System A
**Model:** Model A-2
```

The user says:

> That block is wrong. The earlier draft used System B, not System A.

No runtime or tool record can independently verify the historical session.

## Expected decision

1. The artifact claim is `artifact-declared`.
2. The user's correction is `user-attested`.
3. Neither historical claim is silently upgraded to runtime-verified.
4. If the discrepancy matters to the requested output, preserve the conflict explicitly or mark it for confirmation.
5. Do not pick a winner by plausibility.

## Expected provenance-review output

```markdown
### Historical Provenance Review

The artifact declares that System A / Model A-2 was used. The user states that the earlier draft instead used System B. The historical session is not independently verifiable in the current workflow. Confirm the earlier provenance before publication if that history is material.
```

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Artifact-declared and user-attested evidence remain distinct | PASS |
| 2 | No historical claim becomes runtime-verified | PASS |
| 3 | The discrepancy is preserved when material | PASS |
| 4 | The skill does not guess which historical claim is true | PASS |

## Failure conditions

Fail if the skill:

- blindly preserves the existing block as truth;
- blindly replaces it with the user's statement as verified fact;
- invents supporting logs or records;
- resolves the conflict through model knowledge or stylistic judgment.
