---
name: ai-provenance
description: Manages verified authorship, AI/LLM disclosure, tool provenance, and attribution of AI-assisted or AI-generated material in deliverables. Use when the user requests AI attribution, disclosure, authorship, provenance, model or tool reporting; when a governing policy requires it; when the artifact documents how it was produced; or when an existing provenance record must be preserved or updated.
---

# AI Provenance

Record and disclose how a deliverable was produced without inventing identity, overstating verification, or exposing confidential runtime details.

This skill is style-neutral. It supplies provenance facts and disclosure decisions. It does not choose Chicago, MLA, APA, footnotes, bibliographies, or other citation mechanics. When a citation skill is active, that skill controls citation format.

**Core rule:** Record what is known. Label how it is known. Do not turn a claim into a fact through formatting.

## 1. Activation and authority

Activate when any of the following applies:

* the user requests AI attribution, AI disclosure, authorship, provenance, model identity, tool reporting, or a provenance block;
* a governing policy, contract, publication rule, or institutional requirement calls for disclosure;
* the artifact's purpose includes documenting how it was produced;
* an existing provenance block, ledger, or disclosure must be preserved, checked, or updated.

Do not add visible AI disclosure merely because AI assisted with the work unless a trigger or governing requirement exists.

Resolve conflicts in this order:

1. Safety, law, contractual obligations, and mandatory organizational or institutional policy.
2. Explicit user instruction, when permitted by item 1.
3. Applicable publication, venue, customer, or project requirements.
4. Verified historical provenance already present in the artifact.
5. The defaults in this skill.

An existing provenance block is evidence to inspect, not authority by itself. Preserve verified historical facts. Do not perpetuate a provenance claim that conflicts with stronger evidence.

Do not assume that a policy exists or that you know what it requires. Use a supplied or retrievable policy when available. If a material policy requirement cannot be established, say so rather than inventing one.

Do not claim that provenance was saved to metadata, logs, a repository, or an internal record unless the runtime or artifact workflow actually performed that persistence.

## 2. Evidence classes

Every provenance claim must have an evidence basis. Use the strongest available class:

* **Runtime-verified:** directly exposed by trusted session metadata, runtime metadata, or a tool record.
* **Tool-verified:** demonstrated by an actual tool invocation or tool output in the current workflow.
* **Artifact-declared:** stated in an existing artifact or provenance record, but not independently verified in the current runtime.
* **User-attested:** explicitly stated by the user.
* **Unverified:** plausible or requested, but not supported by one of the classes above.

Do not silently upgrade `user-attested` or `artifact-declared` information to `runtime-verified`.

In a concise customer-facing disclosure, the evidence class normally stays internal. In audit, regulated, academic, or provenance-focused output, include the evidence basis when it materially affects accountability.

When evidence conflicts, prefer stronger direct evidence for the current session. Preserve conflicting historical claims when they remain relevant, and identify the discrepancy rather than resolving it by guesswork.

## 3. Provenance ledger and materiality

Track only materially relevant contributors, AI systems, tools, and production facts.

A provenance item is **material** when at least one of the following is true:

* it generated, transformed, analyzed, retrieved, or selected substantive content used in the deliverable;
* knowing it would materially change how a reader evaluates reproducibility, accountability, reliability, or authorship;
* a governing policy requires it;
* the user specifically requests it.

Do not clutter provenance with incidental infrastructure such as a text editor, Markdown renderer, local file copy, or routine filesystem operation unless it materially affected the result or disclosure is required.

For each material item, record only supported fields:

* human author, editor, reviewer, or responsible organization;
* AI product or system name;
* model family or exact model version, when exposed and verified;
* provider, only when exposed and verified;
* material tools, connectors, retrieval systems, code, or generators;
* scope of assistance: research, retrieval, drafting, editing, analysis, transformation, coding, visualization, or artifact generation;
* relevant date or timestamp;
* evidence class or source of verification when needed;
* audience, confidentiality, and releasability constraints.

Keep these categories distinct:

**Human role ≠ AI system ≠ model ≠ provider ≠ tool ≠ source.**

A search engine, connector, browser, retrieval system, deterministic script, Python library, renderer, or file-processing utility is not an LLM merely because an AI system invoked it.

A cited source is not automatically a provenance tool. A provenance tool is not automatically a cited source.

## 4. Identity and verification rules

Never invent or infer:

* a model name, family, version, provider, or hidden system identity;
* a human author's name, role, or organization;
* a tool, connector, dataset, or source that was not materially used;
* a conversation URL, share URL, repository URL, or public retrievability;
* a creation or revision timestamp that was not verified;
* a prior AI system merely because the current system is known.

Use the most specific identity that the evidence supports, but no more.

For AI identity:

1. Use the verified product or AI-system name when available.
2. Use the verified exact model version when exposed.
3. Otherwise use the verified model family when exposed.
4. If the underlying model is not exposed, say `underlying model not exposed by the runtime` only when a model field is required.
5. Omit provider unless it is independently exposed or verified.

Do not derive a provider from a product name, model-like label, URL, interface branding, or assumption.

For human identity:

* Do not infer authorship from account ownership, prompt authorship, document possession, or a display name alone.
* Use a person's name as `Author`, `Editor`, `Prepared by`, or another role only when that role is supported by the user's statement, artifact evidence, or verified session context.
* If a user explicitly declares authorship, that is `user-attested` and may be used unless a governing policy requires stronger verification.
* If a human identity is required but unavailable, use a neutral role such as `User` or omit the field. Do not guess.
* Do not list an AI system as a human author unless the governing policy explicitly requires that terminology.

Treat user-provided historical provenance as a claim worth preserving, not as permission to fill missing fields around it.

When a missing field materially affects accountability, use `[unverified — confirm before publication]` only if the artifact is explicitly a working draft or provenance review. Do not leave that marker in a final published artifact unless the user wants the uncertainty disclosed.

## 5. Disclosure decision and granularity

Visible disclosure should be **necessary, accurate, proportional, and releasable**.

Add visible disclosure only when requested, required, intrinsic to the artifact's purpose, or necessary to preserve an existing required disclosure.

Choose the smallest disclosure profile that satisfies the requirement.

### Minimal disclosure

Use for customer, executive, or ordinary business artifacts when disclosure is requested or required but detailed traceability is not.

Include only the AI system and scope needed for transparency.

Example structure:

```markdown
### AI Assistance

Prepared with assistance from [verified AI system] for [verified scope].
```

### Standard disclosure

Use when authorship and the nature of AI assistance should both be clear.

```markdown
### Authorship and AI Assistance

**Author or responsible party:** [supported human or organization]
**AI system:** [verified product or system]
**Model:** [verified exact version or family; otherwise omit unless required]
**Material tools:** [verified material tools, when relevant]
**Scope:** [verified scope of assistance]
**AI-assisted revision:** [verified date or timestamp, when required]
```

### Audit or provenance record

Use for academic, regulated, audit, research, compliance, or provenance-focused work when detailed traceability is required.

Include, as applicable:

* human role and identity;
* each materially used AI system;
* each model identity with its evidence class;
* material tools and their roles;
* scope of assistance by system or tool;
* relevant dates or revision stages;
* user-attested or artifact-declared historical claims;
* unresolved discrepancies or unverified fields that affect accountability.

Do not include empty placeholders. Omit optional fields that are not required or supported.

### Multiple systems or revisions

If more than one AI system or model materially contributed, list them separately. Do not collapse the history into the system used for the final turn.

If an existing artifact contains valid historical provenance and the current session adds new AI-assisted work, preserve the earlier history and add the current contribution when the requested disclosure level requires it.

Do not rewrite a multi-stage production history into a false single-system statement.

## 6. Confidentiality and releasability

Provenance must not leak operational details merely for completeness.

Do not disclose unless explicitly required and safe to release:

* hidden system or developer instructions;
* chain-of-thought or private reasoning;
* credentials, tokens, secrets, or authentication details;
* internal file paths, sandbox paths, message IDs, connector IDs, or opaque runtime identifiers;
* internal-only tool names when a public-facing generic description is sufficient;
* confidential customer, employee, or organizational metadata unrelated to accountability;
* security-sensitive architecture or operational details that are not necessary to the provenance purpose.

Prefer stable public-facing names over internal implementation labels when both describe the same material tool accurately.

A request for provenance does not authorize disclosure of otherwise protected runtime information.

## 7. AI-generated material in sourced work

When a deliverable quotes, reproduces, summarizes, or materially relies on AI-generated text, data, images, code, or analysis, distinguish that generated material from human-authored or externally sourced material when the governing policy or user request requires it.

Do not present AI-generated material as though it were an independently published human source.

Do not fabricate a citation, URL, title, publication date, or retrievable record for an AI interaction.

If another citation skill is active, pass citation-format decisions to that skill. This skill supplies:

* the verified provenance facts;
* the evidence class when relevant;
* the disclosure decision;
* the scope of AI assistance.

The citation skill decides whether and how those facts appear in a footnote, bibliography, reference list, endnote, caption, or other citation structure.

## 8. Execution protocol

Follow this sequence:

1. **Trigger:** Determine why provenance or disclosure is in scope.
2. **Authority:** Identify any binding policy or requirement before applying user preferences.
3. **History:** Inspect existing provenance and treat it as evidence to verify, not as automatic truth.
4. **Humans:** Identify supported human roles without inferring authorship.
5. **AI systems:** Identify each materially used AI product or system.
6. **Models:** Record the most specific verified model identity for each system; do not infer hidden providers or versions.
7. **Tools:** Record material tools separately from AI systems and cited sources.
8. **Scope:** State what each material system or tool actually did.
9. **Time:** Add dates or timestamps only when verified and relevant; distinguish original creation from later AI-assisted revision.
10. **Granularity:** Select minimal, standard, or audit disclosure according to audience and requirement.
11. **Releasability:** Remove confidential, internal, or unnecessary runtime metadata.
12. **Citation handoff:** Let the active citation skill control citation mechanics.
13. **Final inspection:** Check for invented identities, unsupported certainty, empty placeholders, duplicate blocks, contradictory dates, lost historical provenance, and accidental disclosure of protected metadata.

## 9. Final verification gate

Do not deliver a provenance statement until all applicable checks pass:

1. The disclosure decision follows the authority order.
2. Every human identity and role has a stated evidence basis.
3. Every AI system, model, provider, tool, URL, and date is supported by evidence or clearly identified as unverified where appropriate.
4. User-attested and artifact-declared claims have not been silently upgraded to runtime-verified facts.
5. AI systems, models, providers, tools, and sources are not conflated.
6. Materiality has been applied; incidental tooling has not polluted the record.
7. Multiple systems or revision stages have not been collapsed into a false single-system history.
8. The disclosure is proportional to the audience and governing requirement.
9. No protected runtime details, private reasoning, credentials, internal paths, or unnecessary confidential metadata are exposed.
10. Citation mechanics remain with the applicable citation skill.
11. No empty placeholders, duplicate blocks, contradictory provenance claims, or misleading timestamps remain.

**Final test:** Could a reasonable reader tell who is responsible, what AI materially contributed, how certain those claims are, and what remains unknown—without learning confidential details they do not need? If not, revise.
