I want you to act as an expert reviewer, editor, and synthesizer of AI chat skills.

I will provide 3 skill files as separate attachments, not pasted into this prompt. The files may be provided as `.zip`, `.skill`, or `.md` files. Each skill will be labeled by its maker (for example: Anthropic, OpenAI, Grok, etc.), and you should use those labels throughout your analysis.

Your job is to compare the three skills thoroughly, one by one, score them rigorously, and then synthesize them into a single best-of-breed skill.

### Core instructions

1. Ingest all attached files before judging any of them.
2. If a file is a `.zip`, open it and identify the actual skill content inside.
   - Prefer the main skill instruction file if there are multiple files.
   - If there is ambiguity about which file is the real skill, state the ambiguity clearly and make the best reasonable determination.
3. Use the maker labels from the files, filenames, or metadata in your writeup wherever possible (for example, “Anthropic skill,” “OpenAI skill,” “Grok skill”) rather than generic numbering.
4. Treat the attached files as the source of truth.
5. Do not ask me to paste the skill markdown unless a file is unreadable.

### Review process

For each skill in turn:

1. Summarize its purpose in 2-4 sentences.
2. Identify its strengths.
3. Identify its weaknesses.
4. Note ambiguities, contradictions, missing guardrails, hidden assumptions, and likely failure modes.
5. Assess:
   - writing quality
   - structure
   - clarity
   - enforceability
   - practicality
   - likely execution reliability
6. Quote short excerpts where useful to support your judgments.

Then compare all three directly across these dimensions:

- clarity of instructions
- completeness
- handling of edge cases
- usefulness in real execution+
- concision vs verbosity
- quality of tool-use guidance
- resistance to hallucination or drift
- maintainability / ease of future editing
- overall likelihood of producing reliable outputs

### Tone and critique standard

- Do not optimize for politeness, diplomacy, or emotional cushioning.
- Be direct, blunt, and specific.
- If a skill is weak, say it is weak.
- If a section is redundant, vague, contradictory, bloated, naïve, or non-operational, label it that way plainly.
- Do not “balance” criticism with praise unless praise is actually warranted.
- Do not soften conclusions with unnecessary hedging.
- Do not treat all three drafts as roughly equal if they are not.
- If one model’s draft is clearly better, say so clearly.
- If one draft is clearly inferior, say so clearly.
- Prioritize discriminating judgment over politeness.

### Strict scoring rubric

Use this 1-10 scale consistently for every dimension:

- 10 = exceptional; precise, comprehensive, highly operational, and hard to misuse
- 9 = excellent; only minor improvements possible
- 8 = strong; clearly above average, with a few notable gaps
- 7 = solid; good overall, but with meaningful weaknesses
- 6 = adequate; usable, but uneven or incomplete
- 5 = mixed; some value, but substantial limitations
- 4 = weak; important deficiencies reduce reliability
- 3 = poor; major problems make it hard to trust
- 2 = very poor; badly flawed, confusing, or unsafe
- 1 = unusable; fails the category almost entirely

Apply these scoring rules:

- Do not give two skills the same score in a category unless they are genuinely close in quality.
- Justify every score in 1-3 sentences with concrete reasons.
- Penalize vague instructions, unenforceable language, redundancy, internal contradiction, hidden assumptions, and weak failure handling.
- Penalize fluff, hedging, generic best-practice language, and instructions that sound good but would fail in practice.
- Reward specificity, operational clarity, realistic tool guidance, explicit guardrails, testability, maintainability, and clear prioritization.
- Score based on how the skill would perform in real use, not on how impressive it sounds.
- If a skill is optimized for one dimension at the cost of another, reflect that tradeoff in the scoring.
- If a skill has a fatal flaw, explicitly call it out and cap the relevant category score appropriately.
- If a draft contains serious design mistakes, do not bury them; elevate them prominently in the review.

### Weighted scoring for final ranking

Use these weights to calculate the final ranking:

- Clarity of instructions — 15%
- Completeness — 10%
- Handling of edge cases — 10%
- Usefulness in real execution — 15%
- Concision vs verbosity — 5%
- Quality of tool-use guidance — 10%
- Resistance to hallucination or drift — 15%
- Maintainability / ease of future editing — 10%
- Overall likelihood of producing reliable outputs — 10%

### Synthesis task

After reviewing and scoring the three original skills:

1. Identify the best specific elements from each skill.
   - what the Anthropic skill does best
   - what the OpenAI skill does best
   - what the Grok skill does best
   - if the labels differ, use the actual labels provided
2. Synthesize the three into one improved final skill that:
   - keeps the strongest wording and structures
   - removes redundancy
   - resolves conflicts and contradictions
   - tightens vague instructions
   - preserves useful constraints and guardrails
   - is clean, coherent, and production-ready
3. Do not create a compromise for compromise’s sake.
4. Build the strongest single version, even if that means discarding large portions of one or more drafts.
5. If the synthesized version requires discarding large sections from a draft, say that explicitly.

### Final recommendation standard

- Give a decisive verdict.
- Name the best original draft, the worst original draft, and why.
- State whether the synthesized final skill is merely cleaner or genuinely superior.
- If one original draft wins mainly because the others failed in important ways, say that plainly.

### Output requirements

Provide all of the following:

1. Executive summary
2. Review of [Maker 1]
3. Review of [Maker 2]
4. Review of [Maker 3]
5. Raw score comparison table
6. Weighted score table and final ranking
7. Best elements to preserve
8. Final synthesized skill
9. Rationale for synthesis
10. Final recommendation

### Scoring output requirements

- Provide one table with raw 1-10 scores by category for each skill.
- Provide a second table with weighted totals.
- Rank the three original skills from best to worst.
- Briefly explain why the top-ranked skill won.
- State whether the synthesized final skill outperforms the top original skill, and why.

### Important requirements

- Treat the attached files as the sole basis for evaluation unless a file is unreadable.
- Be specific, not generic.
- Quote short excerpts from the skills when useful.
- Call out conflicts explicitly.
- Do not flatten meaningful differences.
- Prefer precise, enforceable instructions over aspirational language.
- If one draft is clearly stronger in a category, say so plainly.
- If any draft contains weak, unsafe, redundant, or non-operational instructions, identify them directly.
- If file naming or labeling is inconsistent, explain your interpretation before proceeding.
- Do not be falsely charitable.
- Do not hide major defects behind neutral phrasing.
- Optimize for accurate judgment and useful synthesis, not diplomacy.
