---
name: ai-provenance-regression-suite
target_skill: ai-provenance
type: regression-suite
version: 1.0
tests: 14
---

# AI Provenance Regression Test Suite

## Purpose

This suite tests the decision boundaries and failure modes of the `ai-provenance` skill.

The tests are intentionally adversarial. Each fixture isolates a behavior that should remain stable as the skill evolves.

## Test inventory

| ID | File | Focus |
|---|---|---|
| AP-01 | `01-no-trigger-no-disclosure.md` | No trigger means no unsolicited visible disclosure |
| AP-02 | `02-binding-policy-over-user-suppression.md` | Binding policy outranks user preference |
| AP-03 | `03-user-requested-standard-disclosure.md` | Explicit user-requested disclosure and supported fields |
| AP-04 | `04-model-identity-unavailable.md` | Required model identity when runtime does not expose it |
| AP-05 | `05-conflicting-historical-provenance.md` | Artifact-declared versus user-attested conflict |
| AP-06 | `06-multi-model-revision-history.md` | Multi-system and multi-stage history |
| AP-07 | `07-tools-sources-and-models-separated.md` | AI systems, tools, sources, and incidental infrastructure |
| AP-08 | `08-human-authorship-uncertain.md` | Avoiding inferred human authorship |
| AP-09 | `09-image-generation-and-material-tooling.md` | Generated media and materiality |
| AP-10 | `10-academic-audit-granularity.md` | Detailed academic/audit disclosure |
| AP-11 | `11-confidential-runtime-redaction.md` | Protected runtime details and releasability |
| AP-12 | `12-citation-handoff.md` | Separation of provenance facts from citation mechanics |
| AP-13 | `13-date-and-revision-distinction.md` | Original creation versus later AI-assisted revision |
| AP-14 | `14-existing-block-repair.md` | Repairing an existing block without perpetuating unsupported claims |

## How to use the suite

For each test:

1. Present the fixture to the system with the `ai-provenance` skill active.
2. Capture the provenance decision and visible output.
3. Compare the result with the expected decision, disclosure, and acceptance assertions.
4. Mark the test `PASS` only when every required assertion passes and no failure condition is triggered.
5. When changing the skill, rerun all tests. A change that improves one fixture but breaks another is a regression.

## Recommended pass policy

- **Required:** 14/14 tests pass before merging a skill change.
- Treat a failure involving fabricated identity, policy, model, provider, URL, date, or protected runtime detail as a release blocker.
- Treat formatting differences as non-failures when the underlying provenance facts, evidence status, authority decision, materiality, and releasability are preserved.
- If a fixture exposes a legitimate ambiguity in a governing policy, the correct behavior is to preserve the ambiguity rather than invent a rule.

## Coverage map

| Skill behavior | Covered by |
|---|---|
| Activation | AP-01, AP-03 |
| Authority / policy precedence | AP-02 |
| Evidence classes | AP-03, AP-05, AP-06, AP-10, AP-13, AP-14 |
| Human identity | AP-03, AP-08, AP-14 |
| AI/model/provider identity | AP-04, AP-06, AP-10, AP-14 |
| Materiality | AP-07, AP-09 |
| Multi-system history | AP-05, AP-06, AP-14 |
| Confidentiality / releasability | AP-02, AP-11 |
| Disclosure granularity | AP-02, AP-03, AP-10 |
| AI-generated material | AP-09 |
| Citation handoff | AP-12 |
| Dates and revision stages | AP-13, AP-14 |
| Existing-block preservation/repair | AP-05, AP-14 |

## Maintenance rule

When a new defect is discovered in production, add a regression fixture that fails under the defective behavior before changing the skill. Keep the fixture after the fix so the defect cannot silently return.
