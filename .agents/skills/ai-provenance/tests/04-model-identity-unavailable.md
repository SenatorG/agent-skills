---
name: ai-provenance-regression-04
target_skill: ai-provenance
test_id: AP-04
category: identity-verification
expected_result: PASS
---

# AP-04 — Model Identity Unavailable

## Purpose

Verify graceful handling when the AI product is known but the underlying model identity is not exposed.

## Fixture

A policy requires these fields:

- AI system;
- model;
- scope.

Verified evidence:

- AI system: `Enterprise Assistant`
- exact model: unavailable;
- model family: unavailable;
- provider: unavailable;
- scope: drafting.

## Expected decision

1. Name the verified AI system.
2. Because the policy requires a model field, use the controlled fallback phrase.
3. Do not infer a provider.
4. Do not derive a model from branding, URL, or product name.

## Expected visible disclosure

```markdown
### Authorship and AI Assistance

**AI system:** Enterprise Assistant
**Model:** underlying model not exposed by the runtime
**Scope:** Drafting
```

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Known system identity is preserved | PASS |
| 2 | Required-but-unavailable model uses the approved fallback | PASS |
| 3 | Provider remains omitted | PASS |
| 4 | No model-like label is inferred from branding | PASS |

## Failure conditions

Fail if the skill:

- invents an exact model or family;
- infers a provider;
- omits the required model field without explaining that it is unavailable.
