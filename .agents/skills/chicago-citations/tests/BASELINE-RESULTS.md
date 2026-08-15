# Chicago Citations — Baseline Results

## Target

`chicago-citations` skill, current revised version located in the user's Library.

## Method

Static conformance review of the skill specification against its own stated contract of **Chicago Manual of Style 17th Edition**, with edition-boundary checks against University of Chicago guidance.

This is not a claim that each fixture was independently executed by a separate runtime. It establishes the baseline the runtime test executions should be compared against.

## Result

| Suite | Passed | Total | Status |
|---|---:|---:|---|
| Acceptance | 18 | 20 | BLOCKED |
| Regression | 12 | 12 | PASS |
| Overall | 30 | 32 | BLOCKED |

## Failing acceptance tests

### AC-07 — Book place of publication

The current skill's compact book rule lists author/editor, title, edition, publisher, year, and DOI/URL but not place of publication. For a **CMOS 17** implementation, a supplied/verified place of publication belongs in the book citation. The omission aligns with the later CMOS 18 change that removed the place requirement.

**Remediation:** Add place of publication to the CMOS 17 book metadata pattern when supplied or verified. Do not invent it when absent.

### AC-08 — Edited-book chapter page range

The current skill treats a chapter page range as optional rather than a required terminal-entry element. University of Chicago guidance identifies removal of chapter page ranges from bibliography/reference entries as an **18th-edition change**. Under CMOS 17, the full chapter range belongs in the terminal entry when the chapter is cited as a contribution.

**Remediation:** Require the full contribution page range for CMOS 17 chapter bibliography/reference entries when available, while using the specific cited page(s) in notes or in-text citations.

## Recommended next action

Fix the skill rather than weakening AC-07 or AC-08. Then rerun the full suite and establish a 32/32 baseline.
