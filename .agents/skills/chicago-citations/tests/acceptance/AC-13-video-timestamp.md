---
test_id: AC-13
target_skill: chicago-citations
category: source-type
baseline: PASS
---

# Video / Webinar / Podcast — Timestamp Locator

## Purpose
Confirm timestamp use for a specific audiovisual claim.

## Fixture
A verified video provides:
- speaker;
- title;
- event/channel;
- date;
- platform;
- canonical URL;
- claim at 6:09–6:17.

## Expected behavior
- Preserve the audiovisual source identity.
- Use 6:09–6:17 as the precise locator for the specific claim.
- Do not invent page numbers.

## Pass criteria
- [ ] Timestamp is used.
- [ ] No fake pagination is introduced.
- [ ] URL is canonical or otherwise stable.
