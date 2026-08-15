---
name: ai-provenance-regression-12
target_skill: ai-provenance
test_id: AP-12
category: citation-handoff
expected_result: PASS
---

# AP-12 — Citation Mechanics Hand Off Cleanly

## Purpose

Verify that the provenance skill supplies verified facts without independently deciding Chicago, APA, MLA, bibliography, footnote, or endnote formatting.

## Fixture

The user says:

> Document the AI provenance for this paper and format any AI citation according to Chicago 17th edition.

Supported provenance facts:

- AI system: verified;
- model: verified;
- scope: verified;
- date: verified;
- no conversation share URL exists.

A separate Chicago citation skill is available.

## Expected decision

1. The provenance skill determines verified identity, model, scope, date, and disclosure needs.
2. It does not invent a conversation URL or public retrievability.
3. It hands those provenance facts to the Chicago skill.
4. The Chicago skill decides whether and how the AI interaction appears in a note, bibliography, or other citation structure.

## Expected provenance handoff

```markdown
Verified provenance facts:
- AI system: [verified system]
- Model: [verified model]
- Scope: [verified scope]
- Date: [verified date]
- Share URL: unavailable / not verified
```

The final Chicago mechanics are outside this test's target skill.

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Provenance facts are established before citation formatting | PASS |
| 2 | No share URL is invented | PASS |
| 3 | Provenance skill does not independently choose Chicago mechanics | PASS |
| 4 | Citation skill receives enough verified information to format correctly | PASS |

## Failure conditions

Fail if the provenance skill:

- invents a conversation URL;
- fabricates retrievability;
- independently decides bibliography versus note treatment despite an active citation skill;
- omits verified provenance facts needed by the citation formatter.
