---
test_id: AC-11
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Government Source

## Purpose
Confirm that government authorship, document identifiers, locators, and official URLs remain distinct and traceable.

## Fixture
A government report supplies:
- responsible agency;
- report title;
- report number;
- date;
- relevant page;
- official URL.

## Expected behavior
Use the responsible body as author when appropriate and preserve the report/document identifier, date, locator, and official URL.

## Pass criteria
- [ ] Agency identity is preserved.
- [ ] Report number is not dropped when material.
- [ ] Official URL is preferred.
- [ ] Locator points to the relevant evidence.
