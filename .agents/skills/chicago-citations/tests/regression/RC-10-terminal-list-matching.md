---
test_id: RC-10
target_skill: chicago-citations
category: terminal-sections
baseline: PASS
---

# Author-Date References Must Match Formal Citations

## Defect prevented
Uncited padding in `References` or cited works missing from the terminal list.

## Fixture
The document formally cites sources A, B, and C. Sources D and E were background reading only.

## Required behavior
By default:
- `References` contains A, B, C.
- D and E are omitted or placed in `Further Reading` if requested/useful.

## Pass criteria
- [ ] A, B, C resolve correctly.
- [ ] D and E do not silently appear as formally cited references.
