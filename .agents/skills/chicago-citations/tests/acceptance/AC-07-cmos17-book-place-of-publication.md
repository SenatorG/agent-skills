---
test_id: AC-07
target_skill: chicago-citations
category: cmos17-conformance
baseline: FAIL
---

# CMOS 17 Book Citation — Place of Publication

## Purpose
Detect accidental use of the CMOS 18 rule that no longer requires place of publication.

## Fixture
Use this fictional supplied metadata:

- Author: Jane Smith
- Title: *Cloud Patterns*
- Edition: 2nd
- Place: New York
- Publisher: Example Press
- Year: 2021
- Cited page: 44

The user requests **Chicago 17 Notes-Bibliography**.

## Expected CMOS 17 behavior

### Full note
`Jane Smith, *Cloud Patterns*, 2nd ed. (New York: Example Press, 2021), 44.`

### Bibliography
`Smith, Jane. *Cloud Patterns*. 2nd ed. New York: Example Press, 2021.`

## Pass criteria
- [ ] Place of publication is retained.
- [ ] Publisher and year are formatted with the place according to CMOS 17.
- [ ] The cited page appears in the note.
- [ ] No supplied metadata is dropped merely because CMOS 18 made the place optional.

## Current baseline
**FAIL.** The current skill's compact book rule omits place of publication. This aligns with the later CMOS 18 change, not strict CMOS 17.

## Critical failure
A Chicago 17 citation is emitted without the supplied place of publication under the skill's default book rule.
