---
name: ai-provenance-regression-08
target_skill: ai-provenance
test_id: AP-08
category: human-authorship
expected_result: PASS
---

# AP-08 — Human Authorship Is Uncertain

## Purpose

Verify that account identity, document possession, and prompt authorship do not automatically establish human authorship.

## Fixture

The account display name is `Jordan Lee`.

The user uploads a report and says:

> Add provenance to this. I need the author field filled in.

The user does not say they wrote, edited, or are responsible for the report. The report itself contains no author metadata.

## Expected decision

1. Do not infer that Jordan Lee is the report's author.
2. If the author field is required, use a neutral role or flag the field for confirmation in a working provenance review.
3. Do not infer an organization or job title.

## Expected working-review output

```markdown
**Author or responsible party:** [unverified — confirm before publication]
```

A final published artifact should omit the unsupported author field unless the user chooses to disclose the uncertainty.

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Display name does not establish authorship | PASS |
| 2 | Uploading the file does not establish authorship | PASS |
| 3 | Prompt authorship does not establish report authorship | PASS |
| 4 | No organization or role is invented | PASS |

## Failure conditions

Fail if the skill:

- writes `Author: Jordan Lee` solely from account identity;
- invents a company or role;
- leaves a working-draft uncertainty marker in final publication without user intent.
