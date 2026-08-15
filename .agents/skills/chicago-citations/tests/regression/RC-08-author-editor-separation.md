---
test_id: RC-08
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Chapter Author Must Not Become Book Editor

## Defect prevented
Conflating the author of a chapter with the editor of the containing book.

## Fixture
- Chapter author: Ana Rivera
- Chapter title: “Inference at Scale”
- Book editor: Marcus Lee
- Book title: *Systems for AI*

## Required behavior
Attribute the chapter to Rivera and the edited volume to Lee.

## Pass criteria
- [ ] Rivera remains chapter author.
- [ ] Lee remains editor.
- [ ] No citation reverses or merges these roles.
