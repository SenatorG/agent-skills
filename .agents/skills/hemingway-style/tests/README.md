# Hemingway SalesChat Style — Regression Suite

Baseline skill: `hemingway-style-revised.md`

## Purpose

This suite tests behavior, not exact wording. A style skill may produce different good sentences on different runs. The invariants are what matter: activation, fidelity, attribution, recommendation strength, technical precision, format, customer warmth, controlled implication, and anti-parody discipline.

## How to run

For each test:

1. Load the Hemingway SalesChat skill under test.
2. Submit the **Test prompt** exactly as written.
3. Score the output against the **Pass criteria**.
4. Treat any **Critical failure** as an automatic failure regardless of numeric score.
5. Record notes and the model/version used.

## Scoring

Each test uses binary criteria: `1 = pass`, `0 = fail`.

- **PASS:** all critical criteria pass and the test meets its stated threshold.
- **FAIL:** any critical failure occurs or the score falls below threshold.

Do not reward an output merely because it sounds good. The skill is intended to compress language without compressing meaning.

## Test index

| Test | Focus |
|---|---|
| 01 | Negative activation — ordinary concise prose must not trigger the skill |
| 02 | Positive activation — explicit Hemingway request defaults to H2 / I0 for business prose |
| 03 | Fidelity — numbers, dates, qualifiers, citations, attribution, and recommendation strength |
| 04 | Technical causality — no invented trends, waste, causes, or unsupported conclusions |
| 05 | Format fidelity — preserve scan-friendly bullets, terminology, and qualifiers |
| 06 | Customer warmth — direct prose must not become brusque or commanding |
| 07 | Iceberg control — I2 may imply emotional meaning only where inference is safe |
| 08 | Anti-parody and rhythm — disciplined prose without cosplay, decorative minimalism, or fragment spam |

## Suggested run log

| Date | Model/version | Skill commit | T01 | T02 | T03 | T04 | T05 | T06 | T07 | T08 | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| | | | | | | | | | | | |
