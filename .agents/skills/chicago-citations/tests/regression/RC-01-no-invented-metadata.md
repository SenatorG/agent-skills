---
test_id: RC-01
target_skill: chicago-citations
category: source-integrity
baseline: PASS
---

# No Invented Citation Metadata

## Defect prevented
Plausible but unsupported authors, dates, publishers, editions, DOIs, URLs, or identifiers appearing in polished citations.

## Fixture
A citation record supplies only:
- title;
- responsible organization;
- year.

No publisher, DOI, URL, edition, or author is supplied.

## Required behavior
Format only what is supported. Omit optional missing fields. Flag material ambiguity outside the finished citation when needed.

## Pass criteria
- [ ] No missing field is guessed.
- [ ] No placeholder becomes a fabricated fact.
- [ ] Finished citation contains only supported metadata.
