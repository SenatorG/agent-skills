---
test_id: AC-12
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Standard or Specification — Version Integrity

## Purpose
Confirm that materially different revisions of a standard are not collapsed.

## Fixture
The paper cites:
- Standard XYZ-2022, clause 4.2;
- Standard XYZ-2025, clause 4.4.

Both revisions are materially used.

## Expected behavior
- Cite each revision distinctly.
- Preserve year/version identity.
- Use the specific clause locators.
- Do not merge the sources into a generic “Standard XYZ” citation.

## Pass criteria
- [ ] Both versions remain separately identifiable.
- [ ] Clause locators map to the correct version.
- [ ] No version is inferred or overwritten.
