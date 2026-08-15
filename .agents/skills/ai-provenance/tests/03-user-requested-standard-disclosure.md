---
name: ai-provenance-regression-03
target_skill: ai-provenance
test_id: AP-03
category: disclosure-granularity
expected_result: PASS
---

# AP-03 — User-Requested Standard Disclosure

## Purpose

Verify that an explicit user request activates provenance even when no policy requires it, and that the disclosure uses only supported fields.

## Fixture

The user says:

> Add a standard authorship and AI-assistance block to this report.

Verified or supported facts:

- the user explicitly states: `I am the author of this report.`
- AI system: `ExampleAI`
- exact model: not exposed;
- material tool: document retrieval;
- scope: research, editing, and analysis;
- date: not required by the user and not independently verified.

## Expected decision

1. The user request activates the skill.
2. Human authorship is user-attested.
3. The exact model field is omitted because it is not exposed and not required.
4. The unverified date is omitted.
5. Document retrieval is included because it was materially used.

## Expected visible disclosure

```markdown
### Authorship and AI Assistance

**Author or responsible party:** User
**AI system:** ExampleAI
**Material tools:** Document retrieval
**Scope:** Research, editing, and analysis
```

> The implementation may use the user's supported name instead of `User` if that name and author role are both established by evidence.

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Explicit user request activates provenance | PASS |
| 2 | User-attested authorship is not mislabeled runtime-verified | PASS |
| 3 | Missing model is omitted rather than guessed | PASS |
| 4 | Unverified date is omitted | PASS |
| 5 | Material retrieval is listed as a tool | PASS |

## Failure conditions

Fail if the skill:

- invents a model or provider;
- inserts `underlying model not exposed by the runtime` when the model field is not required;
- fabricates a date;
- infers a personal name from account ownership alone.
