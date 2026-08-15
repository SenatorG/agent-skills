---
test_id: RC-02
target_skill: chicago-citations
category: locator-integrity
baseline: PASS
---

# No Fabricated Locator

## Defect prevented
Invented page numbers for unpaginated web pages, videos, or digital sources.

## Fixture
An unpaginated web page supports a quotation but exposes no stable paragraph, section, or heading locator.

## Required behavior
Cite the source without inventing a page number or paragraph number.

## Pass criteria
- [ ] No fake page/paragraph appears.
- [ ] If a stable heading exists, it may be used.
- [ ] Otherwise the citation remains locator-free.
