---
test_id: AC-16
target_skill: chicago-citations
category: notes-mechanics
baseline: PASS
---

# Full and Shortened Notes

## Purpose
Confirm correct relationship between full notes, shortened notes, and a bibliography.

## Fixture A — No bibliography
The same source is cited twice.

## Expected A
- First note: full citation.
- Later note: shortened citation.

## Fixture B — Full bibliography present
The same source is cited.

## Expected B
- A shortened note may be used from the first citation unless a governing convention requires a full first note.

## Pass criteria
- [ ] Full/shortened behavior changes appropriately with bibliography presence.
- [ ] Shortened notes remain sufficient to identify the source.
- [ ] The system does not mix author-date parentheticals into Notes-Bibliography.
