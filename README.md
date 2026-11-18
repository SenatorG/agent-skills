# agent-skills

A collection of agent skills for AI-assisted writing and deliverables: citation mechanics, AI provenance disclosure, a Hemingway-inspired prose style, and a prompt for comparing and synthesizing skill drafts. Each skill is a standalone Markdown instruction file with YAML frontmatter, with a companion `tests/` folder of acceptance and regression cases.

## Repository layout

```
.agents/skills/
├── Comparison_Synthesis_Revised.md      # Prompt for reviewing and merging three skill drafts
├── ai-provenance/
│   ├── ai-provenance.md                 # The skill
│   └── tests/                           # 14 scenario tests + acceptance test + README
├── chicago-citations/
│   ├── chicago-citations_revised.md     # The skill (CMOS 17th edition)
│   └── tests/
│       ├── acceptance/                  # AC-01 to AC-20
│       ├── regression/                  # RC-01 to RC-12
│       ├── BASELINE-RESULTS.md
│       └── README.md
└── hemingway-style/
    ├── hemingway-style.md               # The skill
    └── tests/                           # 8 scenario tests + README
```

## Skills

### ai-provenance

Records and discloses how a deliverable was produced: which human role is responsible, which AI systems and models contributed, which tools were material, and what each one actually did. It is style-neutral and leaves citation format to the citation skill.

It activates only on a real trigger, such as an explicit user request, a governing policy, a document whose purpose is documenting its production, or an existing provenance block that must be maintained. It does not add disclosure just because AI assisted.

The skill is strict about identity. It forbids inventing model names, providers, authors, URLs, or timestamps, and it keeps user-attested and artifact-declared claims separate from runtime-verified facts. It also limits disclosure to a minimal, standard, or audit profile, and it withholds internal paths, credentials, and other runtime details unless they are required and safe to release.

### chicago-citations

Applies Chicago Manual of Style 17th edition citation mechanics: Author-Date and Notes-Bibliography systems, source ledgers, locators, terminal reference or bibliography sections, and output-format adaptations for Markdown, DOCX, PPTX, spreadsheets, and plain chat.

It has two task modes. FORMAT normalizes metadata the user supplies and never invents missing fields. VERIFY retrieves or inspects sources, validates claims separately from metadata, and checks locators. The skill activates only when Chicago is requested or an existing artifact already uses it.

**Known status:** the test baseline lists two acceptance tests as failing against a strict CMOS 17 target. AC-07 (place of publication for books) and AC-08 (full chapter page range) reflect CMOS 18 defaults, not CMOS 17. The suite marks the skill as release-blocked for strict CMOS 17 conformance until those are fixed. Do not weaken those tests to make the skill pass.

### hemingway-style

An opt-in prose style for any AI chat interface. It borrows Hemingway's craft (concrete nouns, active verbs, compression, deliberate rhythm, controlled implication) without imitating his voice or quoting his wording.

It activates only on an explicit request, such as "Hemingway style," "iceberg," or a direct reference to the skill. Phrases like "make it shorter" do not trigger it. A fidelity contract governs the rewrite: facts, SKUs, prices, citations, qualifiers, and required actions must survive, and the skill never invents detail to make prose more vivid. Style settings are capped at H2 for high-stakes content, and implicitness is I0 by default for specifications, pricing, support, and safety material.

### Comparison_Synthesis_Revised.md

Not a skill itself. It is a reusable prompt that asks a model to review three skill drafts labeled by maker, score each on nine weighted criteria using a strict 1 to 10 rubric, rank them, and produce a single synthesized skill with a rationale. Use it when you have competing drafts and want a structured merge.

## Tests

Each skill ships test cases as Markdown. They are specifications for expected behavior, written to be run against the skill by hand or by a harness. The chicago-citations suite also records a static baseline review (18 of 20 acceptance and 12 of 12 regression at the specification level, before the CMOS 18 fixes). Read that suite's README before running it.

## Usage

Each skill is a plain `.md` file, not a packaged `SKILL.md` folder. To use one, copy or link the skill file into the skills location your agent reads from, and keep its `tests/` folder alongside it if you want to run the acceptance checks. Check the frontmatter `description` to confirm when the skill will trigger.

## Contributing

When a production defect appears, the suite's policy is to add a failing regression fixture first, fix the skill second, and keep the fixture permanently. Acceptance tests should not be weakened to make a change pass.

## License

No license file was found in the repository. Confirm usage rights with the author before reuse or redistribution.
