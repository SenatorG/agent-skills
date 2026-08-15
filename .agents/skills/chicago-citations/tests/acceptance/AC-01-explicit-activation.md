---
test_id: AC-01
target_skill: chicago-citations
category: activation
baseline: PASS
---

# Explicit Chicago Activation

## Purpose
Confirm that an explicit request for Chicago or CMOS activates the skill.

## Fixture
> Format these sources in Chicago 17th edition.

## Expected behavior
- Activate `chicago-citations`.
- Apply CMOS 17 mechanics to the final deliverable.
- Do not require the artifact to already contain Chicago citations.

## Pass criteria
- [ ] Chicago is activated.
- [ ] The output is internally consistent with a selected Chicago system.
- [ ] No unrelated citation style is imposed.

## Critical failure
The system ignores the explicit Chicago request.
