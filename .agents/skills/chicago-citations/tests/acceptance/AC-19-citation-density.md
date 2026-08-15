---
test_id: AC-19
target_skill: chicago-citations
category: citation-density
baseline: PASS
---

# Citation Density

## Purpose
Confirm that citation density scales with audience and evidentiary need.

## Fixture
The same sourced material is requested in:
- executive;
- standard professional;
- academic;
- forensic modes.

## Expected behavior
- Executive: cite material assertions, numbers, quotations, source-dependent conclusions.
- Standard: cite each materially sourced factual or interpretive claim; allow clear short clusters.
- Academic: close citation of substantive factual, analytical, and interpretive claims.
- Forensic: locator-level sourcing for nearly every material assertion or evidentiary step.

## Pass criteria
- [ ] Density changes with the requested mode.
- [ ] Common knowledge and connective prose are not cited merely to increase volume.
