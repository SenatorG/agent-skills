---
test_id: AC-18
target_skill: chicago-citations
category: artifact-behavior
baseline: PASS
---

# Artifact-Aware Citation Mechanics

## Purpose
Confirm that the citation implementation matches what the output format can actually support.

## Fixtures
1. Plain chat asks for footnotes.
2. DOCX asks for footnotes.
3. PPTX asks for Chicago sourcing.
4. Spreadsheet asks for source traceability.

## Expected behavior
- Plain chat: numbered notes or author-date; do not pretend true word-processor footnotes exist.
- DOCX: true footnotes/endnotes when supported.
- PPTX: concise on-slide markers plus full sources in notes/slides/appendix as appropriate.
- Spreadsheet: `Sources` sheet, source columns, cell notes/comments, or a suitable combination.

## Pass criteria
- [ ] No unsupported citation feature is simulated.
- [ ] Citation traceability survives format adaptation.
