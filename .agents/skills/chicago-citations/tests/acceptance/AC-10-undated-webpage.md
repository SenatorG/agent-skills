---
test_id: AC-10
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Undated Web Page — n.d. and Access Date

## Purpose
Confirm correct handling of an undated, changing web page in Author-Date.

## Fixture
A verified web page has:
- responsible organization;
- page title;
- canonical URL;
- no publication or revision date;
- verified access date.

## Expected behavior
- Use `n.d.` where a date position is required.
- Include an access date for the undated/changing source.
- Do not infer a publication date from copyright, search results, or page-generation metadata.

## Pass criteria
- [ ] `n.d.` is used.
- [ ] Access date is included when useful/required.
- [ ] No false publication date is created.
