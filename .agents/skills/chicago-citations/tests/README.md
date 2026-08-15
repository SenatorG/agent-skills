---
name: chicago-citations-test-suite
target_skill: chicago-citations
version: 1.0
acceptance_tests: 20
regression_tests: 12
---

# Chicago Citations — Acceptance and Regression Test Suite

## Purpose

This suite tests the `chicago-citations` skill as a Chicago Manual of Style **17th Edition** implementation.

It has two layers:

- **Acceptance tests (AC):** prove that the skill implements the intended citation behavior and CMOS 17 contract.
- **Regression tests (RC):** lock down failure boundaries so later edits do not reintroduce known classes of defects.

## Important baseline finding

The current skill labels itself CMOS 17, but two compact source-type defaults reflect changes introduced in CMOS 18:

1. the skill's book rule does not require a place of publication;
2. the skill's chapter rule does not require a full chapter page range in the terminal entry.

Those are preserved as failing acceptance tests **AC-07** and **AC-08**. Do not weaken those tests to make the implementation pass. Fix the skill instead.

## Acceptance inventory

| ID | Focus | Baseline |
|---|---|---|
| AC-01 | Explicit activation | PASS |
| AC-02 | No implicit activation | PASS |
| AC-03 | FORMAT mode | PASS |
| AC-04 | VERIFY mode | PASS |
| AC-05 | Author-Date selection | PASS |
| AC-06 | Notes-Bibliography selection | PASS |
| AC-07 | CMOS 17 book place of publication | **FAIL** |
| AC-08 | CMOS 17 chapter page range | **FAIL** |
| AC-09 | Journal article | PASS |
| AC-10 | Undated web page | PASS |
| AC-11 | Government source | PASS |
| AC-12 | Standard/version integrity | PASS |
| AC-13 | Audiovisual timestamp | PASS |
| AC-14 | Personal communication | PASS |
| AC-15 | Same-author/same-year letters | PASS |
| AC-16 | Full and shortened notes | PASS |
| AC-17 | Terminal headings / Further Reading | PASS |
| AC-18 | Artifact-aware mechanics | PASS |
| AC-19 | Citation density | PASS |
| AC-20 | AI provenance handoff | PASS |

## Regression inventory

| ID | Focus | Baseline |
|---|---|---|
| RC-01 | No invented metadata | PASS |
| RC-02 | No fabricated locators | PASS |
| RC-03 | No search-snippet substitution | PASS |
| RC-04 | Metadata ≠ claim support | PASS |
| RC-05 | DOI/canonical URL preference | PASS |
| RC-06 | Conflicting sources | PASS |
| RC-07 | Restricted source metadata | PASS |
| RC-08 | Author/editor separation | PASS |
| RC-09 | Version/revision separation | PASS |
| RC-10 | Terminal-list matching | PASS |
| RC-11 | No fake footnotes | PASS |
| RC-12 | No invented AI provenance | PASS |

## Baseline status

- Acceptance: **18/20 specification-level passes**
- Regression: **12/12 specification-level passes**
- Overall: **30/32**
- Release status for a strict CMOS 17 target: **BLOCKED** until AC-07 and AC-08 are fixed.

This baseline is a **static conformance review of the current skill text**, not a claim that 32 independent runtime generations have been executed.

## Release blockers

Treat these as automatic failures:

- fabricated author, title, date, publisher, edition, version, DOI, URL, locator, or repository identifier;
- fabricated AI provenance or share URL;
- a quotation or number attached to an unverified/invented locator;
- source metadata being mistaken for proof that the source supports the claim;
- materially different source versions collapsed;
- restricted source details leaked to an audience that should not receive them;
- CMOS 18 mechanics silently used when the skill promises CMOS 17.

## Recommended test policy

1. Require **20/20 acceptance tests** before declaring the skill CMOS 17 conformant.
2. Require **12/12 regression tests** before merging any change.
3. Formatting differences may pass only when they remain CMOS 17 compliant and preserve source identity, locator integrity, and terminal-list consistency.
4. Any invented metadata or provenance is a release blocker.
5. When a production defect appears, add a failing regression fixture before changing the skill, then retain that fixture permanently.

## Normative references for edition-boundary tests

Check edition-boundary tests against authoritative University of Chicago sources, especially:
- the CMOS 17 chapters on Notes-Bibliography and Author-Date;
- CMOS Q&A explicitly labeled as relying on the 17th edition;
- University of Chicago documentation identifying changes introduced in the 18th edition.

Do not use a current quick-guide example without confirming whether it reflects CMOS 17 or CMOS 18.
