---
name: ai-provenance-regression-13
target_skill: ai-provenance
test_id: AP-13
category: temporal-provenance
expected_result: PASS
---

# AP-13 — Original Creation Date vs. AI-Assisted Revision Date

## Purpose

Verify that a current revision timestamp is not mislabeled as the original creation date of an older artifact.

## Fixture

Artifact evidence states:

- original document created: March 3, 2025.

Current runtime verifies:

- AI-assisted revision: September 18, 2026, 10:30 a.m. local time.

The user requests a provenance block.

## Expected decision

1. Preserve the historical creation date as artifact-declared unless independently verified.
2. Record the current AI-assisted revision date separately.
3. Do not label the current timestamp as `Generated` if doing so would imply original creation.
4. Do not overwrite the historical date.

## Expected visible disclosure

```markdown
### Authorship and AI Assistance

**Original creation:** March 3, 2025 (artifact-declared)
**AI-assisted revision:** September 18, 2026, 10:30 a.m. local time
```

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Creation and revision dates remain distinct | PASS |
| 2 | Historical date evidence class is preserved | PASS |
| 3 | Current revision date is not mislabeled as original generation | PASS |
| 4 | No date is overwritten for stylistic simplicity | PASS |

## Failure conditions

Fail if the skill:

- replaces the original creation date with the current session time;
- calls the current revision date the original `Generated` date;
- silently upgrades the historical date from artifact-declared to runtime-verified.
