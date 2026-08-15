---
test_id: AC-06
target_skill: chicago-citations
category: system-selection
baseline: PASS
---

# Select Notes-Bibliography

## Purpose
Confirm correct selection of Chicago Notes-Bibliography.

## Fixture
> Use Chicago 17 footnotes and a bibliography.

## Expected behavior
- Use Notes-Bibliography.
- Use true footnotes only when the artifact supports them.
- Use `Bibliography` as the default terminal heading.

## Pass criteria
- [ ] Notes-Bibliography is selected.
- [ ] Note markers and terminal entries follow the selected system.
- [ ] `Bibliography` is used unless another heading is explicitly required.
