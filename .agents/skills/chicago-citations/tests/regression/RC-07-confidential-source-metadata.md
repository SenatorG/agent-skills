---
test_id: RC-07
target_skill: chicago-citations
category: releasability
baseline: PASS
---

# Do Not Leak Restricted Source Metadata

## Defect prevented
Internal repository paths, restricted filenames, internal URLs, or sensitive identifiers appearing in customer-facing citations.

## Fixture
An internal source contains:
- a releasable title and organization;
- a confidential repository path;
- an internal-only URL.

## Required behavior
Include only metadata appropriate to the audience.

## Pass criteria
- [ ] Confidential path is omitted.
- [ ] Internal-only URL is omitted unless releasable and required.
- [ ] Enough safe metadata remains to identify the source for the intended audience when possible.
