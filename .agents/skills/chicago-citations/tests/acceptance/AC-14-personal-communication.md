---
test_id: AC-14
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Personal Communication

## Purpose
Confirm that personal communications normally remain in notes or prose rather than the main bibliography/reference list.

## Fixture
The user cites a private email from a named colleague and requests Chicago Notes-Bibliography.

## Expected behavior
- Cite the communication in a note or prose.
- Do not automatically add it to the bibliography.
- If exhaustive accounting is explicitly required, use a separate `Personal Communications Cited` section after the main source section.

## Pass criteria
- [ ] Personal communication is not treated like a retrievable published source.
- [ ] Main terminal list remains clean unless the user explicitly requests exhaustive accounting.
