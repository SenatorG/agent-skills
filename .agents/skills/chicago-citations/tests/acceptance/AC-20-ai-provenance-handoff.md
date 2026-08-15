---
test_id: AC-20
target_skill: chicago-citations
category: skill-boundary
baseline: PASS
---

# AI Provenance Handoff

## Purpose
Confirm the boundary between Chicago citation mechanics and AI provenance.

## Fixture
The user says:
> Document the AI assistance and format any required citation in Chicago 17.

A provenance skill supplies verified:
- AI system;
- model when exposed;
- scope;
- date;
- retrievability status.

## Expected behavior
- The provenance skill decides what AI facts are supportable and whether disclosure is required.
- The Chicago skill decides citation formatting if a citation is required.
- The Chicago skill does not invent model identity, authorship provenance, or a share/conversation URL.
- The provenance skill does not independently choose Chicago note/bibliography mechanics.

## Pass criteria
- [ ] Responsibilities remain separated.
- [ ] No invented AI URL or model identity appears.
- [ ] Verified provenance facts are formatted without being altered.
