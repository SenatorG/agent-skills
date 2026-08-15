---
test_id: RC-06
target_skill: chicago-citations
category: source-conflict
baseline: PASS
---

# Preserve Credible Source Conflict

## Defect prevented
Silently choosing one of two credible but conflicting sources.

## Fixture
Two authoritative sources report different effective dates for the same rule.

## Required behavior
Represent the disagreement or qualify the claim. Keep each citation attached to the version it supports.

## Pass criteria
- [ ] Conflict is visible when material.
- [ ] No source is silently discarded because one date seems more plausible.
- [ ] Citations remain scoped to their claims.
