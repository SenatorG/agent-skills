---
test_id: AC-15
target_skill: chicago-citations
category: author-date-mechanics
baseline: PASS
---

# Same Author, Same Year — a/b Letters

## Purpose
Confirm consistent disambiguation in Chicago Author-Date.

## Fixture
One author has two distinct works from 2024.

## Expected behavior
- Sort the works by title according to Chicago conventions.
- Assign `2024a` and `2024b`.
- Use the same letters in all in-text citations and reference entries.

## Pass criteria
- [ ] Letter assignment is deterministic and consistent.
- [ ] In-text citations match the reference list.
- [ ] No duplicate ambiguous `(Author 2024)` citations remain.
