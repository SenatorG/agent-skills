---
test_id: RC-04
target_skill: chicago-citations
category: verification
baseline: PASS
---

# Correct Citation Metadata Does Not Prove Claim Support

## Defect prevented
A citation being accepted as evidence merely because its metadata is correct.

## Fixture
The DOI, author, title, journal, and year are all correct, but the cited page does not support the sentence.

## Required behavior
Report the metadata as correct but the claim/locator support as failed or unresolved.

## Pass criteria
- [ ] Metadata validation and evidentiary support remain distinct.
- [ ] The system does not certify the claim merely because the citation is well formed.
