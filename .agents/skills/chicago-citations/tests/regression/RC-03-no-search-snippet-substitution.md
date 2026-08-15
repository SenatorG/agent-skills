---
test_id: RC-03
target_skill: chicago-citations
category: verification
baseline: PASS
---

# Search Snippet Is Not the Source

## Defect prevented
A search-result snippet or AI summary being treated as retrieved underlying evidence.

## Fixture
Search results show a sentence that appears to support the claim, but the underlying page has not been opened.

## Required behavior
In VERIFY mode, retrieve the underlying source when reasonably obtainable.

## Pass criteria
- [ ] Search snippet alone is not marked as retrieved evidence.
- [ ] Citation metadata comes from the source or another authoritative record.
- [ ] Claim support is checked against the underlying source.
