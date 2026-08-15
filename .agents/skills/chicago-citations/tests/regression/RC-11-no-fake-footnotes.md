---
test_id: RC-11
target_skill: chicago-citations
category: artifact-behavior
baseline: PASS
---

# Do Not Pretend Plain Chat Contains True Footnotes

## Defect prevented
Representing plain-text notes as though they were embedded word-processor footnotes.

## Fixture
The user requests Chicago footnotes in plain chat.

## Required behavior
Use numbered notes/endnotes or author-date in plain chat and explain the representation only when the limitation matters.

## Pass criteria
- [ ] No claim of true embedded footnotes is made.
- [ ] Notes remain traceable and readable.
