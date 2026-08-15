---
test_id: AC-05
target_skill: chicago-citations
category: system-selection
baseline: PASS
---

# Select Author-Date

## Purpose
Confirm correct selection of Chicago Author-Date.

## Fixture
> Use Chicago 17 author-date citations for this technical report.

## Expected behavior
- Use parenthetical or narrative author-date citations.
- Use `References` as the default terminal heading.
- Keep the selected system internally consistent.

## Example form
`(Chen 2024, 18–20)`

## Pass criteria
- [ ] Author-Date is selected.
- [ ] In-text citations use author + year + locator when applicable.
- [ ] Terminal heading is `References` unless explicitly overridden.
