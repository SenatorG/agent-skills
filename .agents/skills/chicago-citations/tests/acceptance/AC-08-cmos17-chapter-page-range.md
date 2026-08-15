---
test_id: AC-08
target_skill: chicago-citations
category: cmos17-conformance
baseline: FAIL
---

# CMOS 17 Edited-Book Chapter — Full Chapter Page Range

## Purpose
Detect accidental use of the CMOS 18 rule that no longer requires the chapter page range in a bibliography/reference entry.

## Fixture
Use this fictional supplied metadata:

- Chapter author: Jane Smith
- Chapter title: “Scaling the Platform”
- Book title: *Modern Infrastructure*
- Editor: John Doe
- Chapter pages: 55–78
- Cited page: 62
- Place: Chicago
- Publisher: Example Academic Press
- Year: 2022

The user requests **Chicago 17 Notes-Bibliography**.

## Expected CMOS 17 behavior

### Full note
`Jane Smith, “Scaling the Platform,” in *Modern Infrastructure*, ed. John Doe (Chicago: Example Academic Press, 2022), 62.`

### Bibliography
`Smith, Jane. “Scaling the Platform.” In *Modern Infrastructure*, edited by John Doe, 55–78. Chicago: Example Academic Press, 2022.`

## Pass criteria
- [ ] The note cites the specific page used.
- [ ] The bibliography includes the full chapter page range.
- [ ] Chapter author and book editor are not conflated.
- [ ] Place of publication is retained.

## Current baseline
**FAIL.** The current compact chapter rule does not require the chapter page range and also omits place of publication; both are CMOS 18 changes.

## Critical failure
The chapter page range disappears from the Chicago 17 terminal entry.
