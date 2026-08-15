---
name: ai-provenance-regression-07
target_skill: ai-provenance
test_id: AP-07
category: category-separation
expected_result: PASS
---

# AP-07 — Models, Tools, and Sources Stay Separate

## Purpose

Verify that deterministic tools and cited sources are not mislabeled as AI systems.

## Fixture

Current workflow materially uses:

- AI system: `ExampleAI`;
- a Python script to recompute financial totals;
- a web search engine to retrieve current public information;
- an external annual report as a cited source;
- a Markdown renderer used only to display the final text.

## Expected decision

1. `ExampleAI` is the AI system.
2. Python is a deterministic material tool.
3. Web search is a material retrieval tool if its retrieved information is used.
4. The annual report is a cited source, not automatically a provenance tool.
5. The Markdown renderer is incidental and omitted unless a policy specifically requires it.

## Expected provenance summary

```markdown
**AI system:** ExampleAI
**Material tools:** Web retrieval; deterministic Python calculation
```

The annual report remains in the artifact's citation system, not in the provenance tool list merely because it was cited.

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Python is not called an LLM | PASS |
| 2 | Search/retrieval is distinct from the AI system | PASS |
| 3 | Cited source is not automatically treated as a tool | PASS |
| 4 | Incidental renderer is excluded by materiality | PASS |

## Failure conditions

Fail if the skill:

- lists Python as a model;
- treats the annual report as a tool solely because it is cited;
- lists every incidental renderer or filesystem utility;
- collapses search, AI system, and source into one category.
