---
test_id: RC-05
target_skill: chicago-citations
category: identifier-quality
baseline: PASS
---

# Prefer DOI / Canonical URL Over Tracking Links

## Defect prevented
Long search, session, redirect, or campaign URLs replacing a stable persistent identifier.

## Fixture
A journal article supplies:
- verified DOI;
- publisher URL containing tracking parameters;
- search-result URL.

## Required behavior
Prefer the DOI when appropriate.

## Pass criteria
- [ ] DOI is used.
- [ ] Tracking/search URL is omitted.
- [ ] No alternate URL is invented.
