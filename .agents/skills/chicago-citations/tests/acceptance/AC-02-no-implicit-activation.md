---
test_id: AC-02
target_skill: chicago-citations
category: activation
baseline: PASS
---

# No Implicit Activation from Generic Sourcing

## Purpose
Confirm that Chicago is not imposed merely because a document contains citations, footnotes, references, or sourced prose.

## Fixture
> Clean up this report. Keep its existing APA references.

## Expected behavior
- Do not activate Chicago merely because references exist.
- Preserve the requested or established non-Chicago system.

## Pass criteria
- [ ] No conversion to Chicago occurs.
- [ ] Existing requested citation mechanics are preserved.

## Critical failure
The system converts the artifact to Chicago without an explicit or artifact-based trigger.
