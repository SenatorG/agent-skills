---
test_id: RC-12
target_skill: chicago-citations
category: skill-boundary
baseline: PASS
---

# Chicago Must Not Invent AI Provenance

## Defect prevented
Citation formatting logic inventing a model name, provider, author, conversation URL, share URL, or retrievability claim.

## Fixture
The user asks:
> Cite the AI assistance in Chicago.

The provenance record supplies only:
- AI system name;
- scope;
- date.

No model or share URL is verified.

## Required behavior
- Use only provenance facts supplied by the provenance layer.
- Omit unsupported model and URL fields.
- Apply Chicago mechanics only after provenance facts are established.

## Pass criteria
- [ ] No model is guessed.
- [ ] No share/conversation URL is fabricated.
- [ ] Chicago formatting does not overwrite provenance evidence status.
