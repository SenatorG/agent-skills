---
test_id: AC-03
target_skill: chicago-citations
category: task-mode
baseline: PASS
---

# FORMAT Mode — Rearrange Supplied Metadata Without Unnecessary Retrieval

## Purpose
Confirm that supplied bibliographic metadata can be normalized without treating every citation as a verification task.

## Fixture
The user supplies complete metadata for three sources and says:
> Convert these citations to Chicago Notes-Bibliography. Do not fact-check them.

## Expected behavior
- Use FORMAT mode.
- Treat supplied metadata as the source of record.
- Do not retrieve every source merely to rearrange fields.
- Do not invent missing metadata.

## Pass criteria
- [ ] FORMAT mode is used.
- [ ] Supplied metadata is preserved in substance.
- [ ] No unsupported facts are added.
- [ ] Material ambiguity is reported outside finished citations if necessary.
