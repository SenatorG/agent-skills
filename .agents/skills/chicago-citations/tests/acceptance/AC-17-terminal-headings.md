---
test_id: AC-17
target_skill: chicago-citations
category: terminal-sections
baseline: PASS
---

# Terminal Source Headings and Uncited Background Material

## Purpose
Confirm correct source-section naming and separation of uncited recommendations.

## Fixture
The user requests Author-Date and also supplies three uncited background readings.

## Expected behavior
- Use `References` for formally cited works.
- Put uncited recommended sources in `Further Reading` when useful.
- Use `Works Cited` only if explicitly required.

## Pass criteria
- [ ] Cited and uncited works are not silently mixed when the user's intent is citation-matched references.
- [ ] Heading names follow the selected system.
