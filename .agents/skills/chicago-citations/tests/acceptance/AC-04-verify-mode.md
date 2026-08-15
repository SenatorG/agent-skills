---
test_id: AC-04
target_skill: chicago-citations
category: task-mode
baseline: PASS
---

# VERIFY Mode — Metadata and Claim Support

## Purpose
Confirm that verification requires inspection of the underlying source and separate validation of citation metadata and claim support.

## Fixture
> Verify that this citation is correct and that page 44 supports the quoted claim.

## Expected behavior
- Use VERIFY mode.
- Retrieve or inspect the source when available.
- Confirm metadata separately from whether page 44 supports the claim.
- Verify the locator and quotation.

## Pass criteria
- [ ] Source inspection occurs.
- [ ] Metadata validation and claim-support validation are separate checks.
- [ ] The locator is not accepted merely because the citation looks plausible.
- [ ] Unsupported claims are qualified or rejected.
