---
name: ai-provenance-regression-09
target_skill: ai-provenance
test_id: AP-09
category: generated-media
expected_result: PASS
---

# AP-09 — Image Generation Is Material Provenance

## Purpose

Verify that substantive image generation or transformation is recorded when provenance disclosure is in scope, while incidental file handling is omitted.

## Fixture

A marketing one-pager contains:

- human-written copy;
- an AI-generated hero image produced by `Image System X`;
- final layout assembled by `Assistant Y`;
- a local file copy and image-format conversion used only to package the deliverable.

The user asks for a provenance record.

Verified evidence supports the two AI system names, but no exact model versions.

## Expected decision

1. Record `Image System X` separately for image generation.
2. Record `Assistant Y` separately for layout/artifact generation if materially responsible.
3. Omit exact model fields because they are not verified.
4. Omit routine local file copy and format conversion unless they materially affected the result.
5. Do not describe generated image content as a human-authored source.

## Expected provenance record

```markdown
### AI Provenance

- **Image System X:** Image generation.
- **Assistant Y:** Artifact layout and generation.
```

## Acceptance assertions

| # | Assertion | Expected |
|---|---|---|
| 1 | Material image generation is recorded | PASS |
| 2 | Multiple AI systems remain separate | PASS |
| 3 | Unverified model versions are omitted | PASS |
| 4 | Incidental packaging operations are excluded | PASS |

## Failure conditions

Fail if the skill:

- hides material image generation from a requested provenance record;
- invents model versions;
- lists file-copy operations as substantive AI systems;
- presents the generated image as an independently published human source.
