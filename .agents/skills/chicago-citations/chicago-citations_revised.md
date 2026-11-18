---
name: chicago-citations
description: Applies Chicago Manual of Style 17th Edition citation systems, source validation, citation placement, bibliography or reference-list construction, and artifact-aware citation mechanics. Use when the user explicitly requests Chicago or CMOS, requests conversion to Chicago, or an existing artifact consistently uses Chicago.
---

# Chicago Citations

Apply CMOS 17 to the final deliverable when this skill is activated. This skill controls citation-system selection, source validation, citation density, source formatting, locator choice, and terminal source lists.

Do not decide whether to disclose AI assistance, authorship provenance, model identity, or model version. Use a separate provenance or AI-attribution skill for those concerns.

## Activation and precedence

Activate when the user explicitly requests Chicago or CMOS, requests conversion to Chicago, or asks you to continue or revise an artifact that consistently uses Chicago.

Do not impose Chicago merely because the work is sourced, contains footnotes, uses a bibliography, or includes references.

Resolve conflicts in this order:

1. Explicit user instruction.
2. Governing institutional, publication, customer, course, or artifact requirement.
3. A consistent citation system already present in the artifact.
4. The defaults below.

If the user requests a conversion, normalize the artifact consistently. If an artifact mixes systems and the user did not request conversion, preserve the governing or dominant system and flag the inconsistency when it could affect publication or grading.

## Choose the task mode

### FORMAT

Use when the user supplies citations or bibliographic metadata and asks you to format, normalize, convert, or clean them up.

* Treat supplied metadata as the source of record unless verification is requested.
* Do not retrieve every source merely to rearrange known metadata.
* Never invent missing metadata.
* Retrieve a source only when a material ambiguity cannot be resolved safely from the supplied record.
* Omit fields CMOS permits you to omit; flag material unresolved metadata outside the finished citation.

### VERIFY

Use when the user asks you to research, substantiate, validate, correct, fact-check, build citations from sources, or confirm that citations support claims.

* Retrieve or inspect the underlying sources.
* Maintain a source ledger for materially used sources.
* Validate citation metadata separately from claim support.
* Verify locators for quotations, numbers, contested claims, and source-dependent conclusions.
* Prefer authoritative and primary sources appropriate to the claim.

For mixed tasks, use VERIFY only for the sources or claims that actually require it.

## Select the citation system

* Use **Author-Date** when the user requests author-date, inline, in-text, or parenthetical citations, or when analytical, scientific, technical, or business prose has no stronger convention.
* Use **Notes-Bibliography** when the user requests footnotes, endnotes, notes, humanities-style documentation, or source commentary outside the running prose.
* Use the system already present in a consistent artifact unless a higher-precedence rule requires a change.

Terminal headings:

* Author-Date: `References` by default.
* Notes-Bibliography: `Bibliography` by default.
* Use `Works Cited` only when explicitly required.
* Use `Further Reading` for uncited background sources when useful.

## Source ledger

In VERIFY mode, record only supplied or verified information for each materially used source:

* author, editor, or responsible organization;
* title and subtitle;
* container, publication, repository, platform, or site;
* publication, revision, release, or update date;
* edition or version when material;
* locator: page, section, chapter, paragraph, timestamp, slide, figure, table, item, or file path;
* DOI, permalink, canonical URL, or stable internal link;
* source type;
* access date when useful for a changing or undated source;
* retrieval status: retrieved in this task, supplied by the user, or not retrieved;
* evidence notes: authority, currency, conflicts, and releasability.

A supplied attachment counts as retrieved only if it is readable and actually inspected. A remembered source, unexplained cached value, search-result snippet, or AI-generated summary does not count as retrieved evidence.

## Execution protocol

In VERIFY mode, use retrieval, document-reading, and file-processing tools rather than memory when the source can be inspected.

1. Identify the exact sources or claims that require evidence.
2. For archives, list members before reading payloads. Read only relevant members. Never execute extracted binaries, scripts, installers, or unknown executables.
3. Prefer the main source document over ancillary, cached, or derivative files unless those are materially relevant.
4. For large sources, retrieve only relevant pages or sections when supported. If unreadable, try one alternate representation, then flag the limitation instead of guessing.
5. Persist the source ledger through drafting and verification.
6. Inspect the final artifact for broken notes, links, headings, tables, source sections, unsupported citation mechanics, and unresolved source issues.

## Source integrity and validation

Never invent an author, title, date, publisher, edition, version, locator, DOI, URL, repository identifier, or other citation metadata.

In VERIFY mode, every DOI, URL, page, date, and locator printed in the deliverable must trace to a source actually retrieved or supplied for the task.

If a field cannot be verified, retrieve the source when practical, omit fields CMOS permits you to omit, preserve the identifiable citation using verified metadata, and report material uncertainty in `Source notes` rather than inside the finished citation.

Never use a search-result snippet, AI summary, citation aggregator, or secondary reference as a substitute for an accessible underlying source when the underlying source can reasonably be obtained.

Prefer source metadata over snippets, DOI or another persistent identifier over a generic URL when appropriate, and canonical URLs over search-result, redirect, session, or tracking URLs. Cite the version actually used when versions differ materially.

Validate the source separately from the citation. Confirm that the source supports the claim, the locator points to the relevant evidence, the source is fit for the claim, quotations are exact, numerical values and units match, and material context has not been removed.

For vendor-specific claims, prefer official vendor documentation. For laws, standards, regulations, government actions, and technical specifications, prefer authoritative primary sources when available.

When credible sources conflict, represent the disagreement or qualify the claim; do not silently choose one.

For restricted company sources, include only metadata appropriate to the intended audience. Do not expose confidential repository details, internal URLs, restricted filenames, or unreleasable claims in a customer-facing artifact.

## Locator rules

Use the most stable and precise locator available. Prefer:

1. page number or range;
2. numbered section, chapter, clause, or paragraph;
3. figure, table, appendix, or item number;
4. timestamp or range;
5. slide number;
6. heading or subheading;
7. another stable source-specific locator.

Do not invent page numbers for unpaginated sources. For quotations and precise numerical claims, use a locator whenever the source provides one. For unpaginated web sources, cite without fabricating a locator unless a stable section, paragraph, heading, or other useful locator exists.

## Source-type rules

Apply these compact defaults unless the governing convention requires otherwise.

### Books and chapters

* **Book:** author/editor; title; edition when relevant; publisher; year; DOI or stable URL when useful.
* **Chapter:** chapter author; chapter title; book title; editor(s); chapter page range when available; publisher; year; DOI or stable URL.
* Do not invent a publication city or confuse a chapter author with a book editor.

### Journal and conference works

* **Journal article:** author; article title; journal; volume; issue when available and relevant; year; page range or article number; DOI preferred over a generic URL.
* **Conference work:** distinguish a published proceedings paper, unpublished conference paper/presentation, and slide deck. Include event, proceedings, publisher, date, DOI, or URL only when they apply to the source actually used.

### Web, corporate, and technical sources

* **Web page:** author or responsible organization; page title; site/platform when distinct; publication or update date when supplied; canonical URL; access date when undated, changing, or required.
* Do not infer publication dates from copyright footers, search-engine dates, or page-generation metadata.
* **Corporate/vendor document:** organization or author; title; document type when useful; version/release when material; date; document number when useful; canonical URL.
* For product capability, compatibility, sizing, performance, lifecycle, or configuration claims, cite the documentation version that supports the claim.

### Government, standards, and specifications

* **Government source:** responsible body; title; report/document/statute/rule/case/series identifier when present; date; locator when material; official URL or persistent identifier.
* **Standard/specification:** standards body; identifier; title; edition/revision/version; year or release date; clause/section/table/figure locator when needed; DOI or official stable URL.
* Do not collapse materially different revisions into one citation.

### Data, software, and repositories

* **Dataset:** creator/organization; title; version/release; date; repository/platform; DOI or persistent identifier; access date for changing unversioned data.
* **Software/repository:** author/maintainer/organization; software or repository title; version/release/tag/commit/branch when material; platform; release/commit date when available; canonical URL.
* Prefer a stable release, tag, commit, or archived record over a moving default branch when exact code state matters.

### Audiovisual, presentations, and unpublished material

* **Video/webinar/podcast:** creator, speaker, host, or organization; title; series/channel/event when relevant; date; platform; URL; timestamp for specific material.
* **Presentation/slides:** presenter/organization; title; event/course/venue when useful; date; slide number for specific claims; stable URL or releasable internal locator.
* **Internal/unpublished:** include only metadata needed to identify the source for the intended audience. Do not expose confidential paths, repository structures, addresses, or identifiers without need.
* **Personal communications:** normally cite in notes or prose rather than the terminal list. If exhaustive accounting is explicitly required, add `Personal Communications Cited` after the main source section.

## Missing and ambiguous metadata

* Use `n.d.` when no publication date is available in Author-Date and a date position is required.
* Do not invent an author; when none is identifiable, begin with the title as CMOS permits.
* Do not infer an edition, version, issue, publisher, or publication date from context alone.
* Do not treat a copyright year as the publication year unless the source presents it that way.
* Preserve supplied names as published unless normalization is requested and identity is clear.
* If two records may be the same source but cannot be safely reconciled, keep them distinct and flag the ambiguity.

## Citation density

Use the least intrusive density that preserves traceability:

* **Executive:** cite material assertions, numbers, quotations, and source-dependent conclusions.
* **Standard:** cite each materially sourced factual or interpretive claim. One citation may support a short, unambiguous cluster of consecutive sentences from the same evidence.
* **Academic:** cite substantive factual, analytical, and interpretive claims closely enough for a reader to trace the evidence without guessing.
* **Forensic:** use locator-level sourcing for nearly every material assertion, quotation, number, contested interpretation, or evidentiary step.

Do not cite common knowledge, connective prose, clearly labeled original analysis, or the user's own stated facts merely to create citation volume.

If unspecified, use Standard for sourced professional prose and Academic for formal academic work.

## Citation mechanics

### Author-Date

Use `(Chen 2024, 18–20)` or `Chen (2024, 18–20)`. Place citations before terminal punctuation unless grammar, a quotation, or the artifact's established convention requires otherwise.

For multiple works in one parenthetical citation, separate works with semicolons. Order them according to their relationship to the prose or relative importance when that matters; otherwise use a consistent alphabetical or chronological order.

Use `n.d.` when no date is available. For same-author, same-year works, assign `a`, `b`, and later letters after sorting the works by title according to Chicago conventions, and use the same letters throughout.

### Notes-Bibliography

Place superscript note numbers after punctuation unless the governing convention requires another placement.

When no bibliography supplies full publication details, use a full note at first citation and shortened notes thereafter. When a full bibliography is present, shortened notes may be used from the first citation unless the user, institution, publication, or artifact convention requires full first notes.

Use footnotes when the output supports true footnotes. Otherwise use endnotes or numbered notes; do not pretend plain text or chat contains true word-processor footnotes.

## Terminal source sections

### Author-Date

`References` should correspond to formally cited works. Include cited works and avoid uncited padding unless the user explicitly requests additional reading.

Alphabetize by author surname or responsible organization. Alphabetize no-author works by title, ignoring initial articles according to Chicago conventions.

### Notes-Bibliography

A `Bibliography` may include works cited in notes, other works consulted when expected, or a selective set appropriate to the artifact. Do not assume every work mentioned tangentially in a note must appear when the governing convention allows otherwise.

If the user wants only cited sources, keep the bibliography citation-matched. Put uncited recommended sources in `Further Reading` when that improves clarity.

Personal communications normally remain in notes or prose.

## Output-format behavior

Adapt mechanics to the artifact. Do not simulate unsupported features:

* **Markdown:** use Markdown footnotes when supported; otherwise numbered notes or author-date.
* **HTML:** use accessible linked note markers and backlinks when practical.
* **DOCX:** use true footnotes/endnotes when supported and hanging indents for terminal entries.
* **PPTX:** use concise on-slide citations or source markers plus full source slides, speaker notes, or an appendix.
* **Spreadsheet:** use a `Sources` sheet, source columns, cell notes/comments, or a suitable combination.
* **Plain chat:** use author-date parentheticals or numbered notes rather than pretending to create true footnotes.
* **PDF:** preserve the source document's citation mechanics or those of the generating format; do not remove locators during conversion.

When an artifact cannot support the requested feature exactly, use the closest faithful representation and state the limitation only when it matters.

## Final verification gate

Do not deliver until all applicable checks pass:

1. Activation and precedence were applied correctly.
2. FORMAT or VERIFY mode was chosen only as broadly as needed.
3. The selected citation system is internally consistent.
4. Materially sourced claims have citations appropriate to the chosen density.
5. Quotations, numbers, contested claims, and source-dependent conclusions have precise locators when available and useful.
6. Citations and notes resolve to terminal entries when the selected system requires that relationship.
7. Author-Date references correspond to cited works unless the user explicitly requests otherwise.
8. Notes-Bibliography terminal entries match the intended scope.
9. No citation contains invented metadata.
10. Same-author/same-year letters, heading choice, alphabetical order, title treatment, dates, locators, DOI/URL, and edition/version fields are consistent.
11. No verification warning appears inside a finished citation unless the user explicitly requested an editorial working draft.
12. Material unresolved metadata, source conflict, releasability issue, or unverified locator appears in a short `Source notes` section.
13. Authorship and AI-assistance disclosure are left to the separate provenance or AI-attribution policy unless explicit instructions require otherwise.
