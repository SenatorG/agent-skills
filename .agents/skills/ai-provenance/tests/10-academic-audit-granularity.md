---
name: ai-provenance-regression-10
target_skill: ai-provenance
test_id: AP-10
category: audit-granularity
expected_result: PASS
---

# AP-10 — Academic / Audit Granularity

## Purpose

Verify that provenance-focused work can disclose evidence classes and system/tool scope in more detail than a customer-facing artifact.

## Fixture

A research methods appendix must document AI assistance.

Supported evidence:

- Researcher name and role: user-attested;
- AI system: runtime-verified `Research Assistant X`;
- model family: runtime-verified `RX-4`;
- exact model version: not exposed;
- literature retrieval connector: tool-verified;
- Python analysis script: tool-verified;
- scope: literature retrieval, statistical analysis, copyediting;
- date of current revision: runtime-verified.

## Expected decision

1. Use the audit/provenance profile.
2. Include the evidence basis where it materially affects accountability.
3. Include the verified model family but not an invented exact version.
4. List retrieval and Python separately from the AI system.
5. Keep citation-format decisions outside this skill.

## Expected audit record

```markdown
### AI Provenance

- **Researcher:** [supported researcher identity]. Evidence: user-attested.
- **AI system:** Research Assistant X. Evidence: runtime-verified.
- **Model family:** RX-4. Evidence: runtime-verified.
- **Material tool:** Literature retrieval connector. Role: retrieval. Evidence: tool-verified.
- **Material tool:** Python analysis script. Role: statistical analysis. Evidence: tool-verified.
- **AI scope:** Copyediting and analytical assistance.
- **Revision date:** [verified current revision date].
```

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Audit profile is more detailed than minimal disclosure | PASS |
| 2 | Evidence basis is exposed where accountability benefits | PASS |
| 3 | Exact model version is not invented | PASS |
| 4 | Tools remain distinct from the AI system | PASS |
| 5 | Citation mechanics are deferred to the citation skill | PASS |

## Failure conditions

Fail if the skill:

- uses only a vague one-line disclosure despite an audit requirement;
- invents an exact model version;
- hides material tools;
- formats bibliography or citation mechanics itself without a separate citation instruction.
