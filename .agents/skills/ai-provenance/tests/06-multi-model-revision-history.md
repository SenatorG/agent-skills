---
name: ai-provenance-regression-06
target_skill: ai-provenance
test_id: AP-06
category: multi-system-history
expected_result: PASS
---

# AP-06 — Multi-Model Revision History

## Purpose

Verify that materially distinct AI stages remain separate rather than being collapsed into the final model used.

## Fixture

Supported production history:

- Stage 1: user-attested use of `System Alpha` for brainstorming;
- Stage 2: artifact-declared use of `System Beta / Model B7` for drafting;
- Stage 3: current runtime verifies `System Gamma / Model G3` for analysis and final editing.

The user asks for an audit-oriented provenance record.

## Expected decision

1. List all materially relevant stages separately.
2. Label the evidence basis where it affects accountability.
3. Do not imply that System Gamma created the entire artifact.
4. Do not silently convert historical claims into runtime-verified facts.

## Expected audit record

```markdown
### AI Provenance

- **Stage 1 — Brainstorming:** System Alpha. Evidence: user-attested.
- **Stage 2 — Drafting:** System Beta / Model B7. Evidence: artifact-declared.
- **Stage 3 — Analysis and final editing:** System Gamma / Model G3. Evidence: runtime-verified.
```

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Each material AI stage is listed separately | PASS |
| 2 | Evidence classes remain distinct | PASS |
| 3 | Final-session AI does not absorb prior history | PASS |
| 4 | Scope is associated with the correct stage | PASS |

## Failure conditions

Fail if the skill:

- states only `System Gamma / Model G3`;
- describes all stages as runtime-verified;
- combines scopes in a way that falsely attributes earlier work to the current system.
