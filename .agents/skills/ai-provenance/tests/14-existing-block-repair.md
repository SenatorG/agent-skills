---
name: ai-provenance-regression-14
target_skill: ai-provenance
test_id: AP-14
category: block-repair
expected_result: PASS
---

# AP-14 — Repair an Existing Provenance Block

## Purpose

Verify that the skill preserves supported historical provenance while removing unsupported claims and avoiding duplicate disclosure blocks.

## Fixture

The artifact contains:

```markdown
### Authorship and AI Assistance

**Author:** Taylor Morgan
**AI system:** ExampleAI
**Model:** X-99 Ultra
**Provider:** ExampleCorp
**Share URL:** https://example.invalid/conversation/123
**Generated:** January 1, 2026
```

Current evidence establishes:

- user-attested author: Taylor Morgan;
- runtime-verified AI system: ExampleAI;
- model version: not exposed;
- provider: not independently verified;
- share URL: not verified;
- January 1, 2026 is artifact-declared historical provenance;
- current revision adds editing but does not establish the original model.

## Expected decision

1. Preserve supported authorship with its proper evidence status.
2. Preserve the verified AI system.
3. Remove or qualify unsupported model, provider, and share URL claims.
4. Preserve the historical date as artifact-declared if relevant.
5. Add current revision provenance only if required by the disclosure profile.
6. Update the existing block rather than appending a duplicate.

## Expected repaired block

```markdown
### Authorship and AI Assistance

**Author:** Taylor Morgan
**AI system:** ExampleAI
**Original provenance date:** January 1, 2026 (artifact-declared)
**Current scope:** Editing
```

If the governing requirement needs the unresolved historical model identity, record it in a provenance review rather than presenting `X-99 Ultra` as verified.

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Existing block is inspected rather than trusted wholesale | PASS |
| 2 | Unsupported model/provider/URL claims are not perpetuated | PASS |
| 3 | Supported historical date can be preserved with evidence status | PASS |
| 4 | Current scope can be added without falsifying original history | PASS |
| 5 | No duplicate provenance block is created | PASS |

## Failure conditions

Fail if the skill:

- preserves all existing fields merely because they are already present;
- appends a second disclosure block instead of repairing the first;
- upgrades unsupported historical claims to verified facts;
- deletes supported history unnecessarily.
