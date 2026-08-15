---
test_id: AC-09
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Journal Article — Volume, Issue, Article Range, DOI, and Specific Locator

## Purpose
Confirm correct treatment of journal metadata and locator scope.

## Fixture
Supplied metadata includes:
- two authors;
- article title;
- journal title;
- volume 12;
- issue 3;
- year 2024;
- article pages 201–226;
- cited pages 214–15;
- verified DOI.

## Expected behavior
- Preserve both authors.
- Include journal, volume, issue, year, and article range in the terminal entry.
- Use 214–15 for the specific claim locator.
- Prefer the verified DOI over a generic article URL.

## Pass criteria
- [ ] Article range and claim locator are not confused.
- [ ] DOI is preserved.
- [ ] No invented issue, page, or URL appears.
