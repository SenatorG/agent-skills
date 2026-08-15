---
test_id: RC-09
target_skill: chicago-citations
category: version-control
baseline: PASS
---

# Do Not Collapse Materially Different Editions or Revisions

## Defect prevented
Two materially cited editions, standards, software releases, or document versions being deduplicated into one generic entry.

## Fixture
The analysis uses version 2.1 for one claim and version 3.0 for another.

## Required behavior
Keep both versions separately identifiable and attach the correct locator to each.

## Pass criteria
- [ ] Version identities remain distinct.
- [ ] No generic merged citation replaces them.
- [ ] Each claim resolves to the version actually used.
