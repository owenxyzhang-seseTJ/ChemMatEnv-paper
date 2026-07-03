---
name: top-journal-review-cycle
description: "Use whenever the user is preparing a materials, chemistry, porous-materials, or energy/environment manuscript for a top journal: building a paper story from evidence, researching target-journal requirements, drafting English sections, calibrating phrasing against same-topic top-journal papers, de-AI-ing prose, rebuilding sentence/paragraph logic, writing cover letters, responding to reviewer comments, or running pre-submission review cycles. Trigger even when the user does not say 'top journal' — mentions of pre-submission checks, reviewer response, overclaim fixes, logic repair, story design, or de-AI should all fire this skill. 适用于材料、化学、多孔材料、能源环境论文的故事设计、目标期刊要求检索、英文起草、顶刊表达校准、去 AI 味、逻辑重建、cover letter、审稿意见回复和投稿前审稿循环；用户说到投稿前检查、回复审稿人、overclaim、逻辑重建、故事设计或去 AI 味时即应触发，不必出现'顶刊'字样。"
---

# Top Journal Review Cycle

This skill runs an end-to-end manuscript workflow for materials and chemistry papers: story-package design, target-journal requirements research, journal-aware drafting, mandatory quality gates, and multi-round top-journal review simulation. It is designed for manuscript building and pressure testing, not generic polishing.

## Core Rule

Every time manuscript text is drafted or revised, run the quality gates that match the scale of the change, and revise the text before moving on. The three gates:

1. **Live literature expression audit** — `references/live-literature-expression-audit.md`: search target-journal, same-topic, or adjacent top-journal papers for natural phrasing, collocations, discourse moves, and claim strength.
2. **Anti-AI audit** — `references/anti-ai-style-rules.md`: remove generic praise, template transitions, over-smoothed rhythm, and mechanical paragraph shapes.
3. **Logic-link audit** — `references/logic-link-audit.md`: make sentence and paragraph relations defensible; repair missing bridges, false causality, and unsupported jumps.

**Gate level matches the change, not a fixed loop.** Running a full live literature search on every small wording tweak wastes effort and encourages circular searching. Use:

- **Full gate (all three, including live literature search):** after new drafting, after structural revisions, and on the final pass before review simulation. The pre-draft same-topic search (step 5) counts toward this; do not re-search the same topic again within the same session unless the section type or concept genuinely changed.
- **Light gate (anti-AI + logic only, no new live search):** for small wording fixes, hedge tightening, or paragraph reshaping that does not introduce new claims. Reuse the session's existing expression-audit results.

Do not continue to editor or reviewer simulation until the current text has passed the appropriate gate level.

Before drafting new manuscript text, also complete:

1. **Story architecture**: convert evidence into a locked story package.
2. **Live target-journal requirements research**: search official author guidelines and record format constraints.
3. **Live same-topic expression research**: search same-topic top-journal papers for collocations, section moves, hedge strength, and evidence verbs.
4. **Journal-aware drafting**: draft only from the locked story package, live journal requirements, evidence map, and same-topic top-journal expression patterns.

## Inputs

Accept any of the following:

- Existing manuscript text, section draft, abstract, introduction, or cover letter.
- Data summaries, figure legends, slides, tables, or an evidence map.
- Target journal or journal family.
- Existing `story_package`.
- Reviewer comments or editor decision letters.

If the user only provides raw materials and asks for polished writing, first build or request a minimal `story_package`.

## Required Story Package

Before drafting a major section or making structural revisions, lock:

- `core_problem`
- `specific_bottleneck`
- `design_principle`
- `main_claims`
- `evidence_map`
- `mechanism_position`
- `scope_limits`
- `target_journal_profile`

Use `references/story-package-schema.md`. If the story changes, stop writing and rebuild the story package.

## Required Journal Requirements Packet

Before drafting for a named target journal, perform live search and record:

- target journal and article type
- official author-guidelines URL
- title limit
- abstract format and word limit
- main-text word or page limit
- display item limits
- reference limits or style
- required sections, statements, reporting summaries, graphical abstract, TOC graphic, or SI rules
- template availability and URL if present

Use `references/target-journal-requirements.md`. If live search is unavailable, do not perform target-journal-specific drafting; ask the user to enable search or provide official guidelines and same-topic reference papers. If the target journal is unknown, draft only against a declared journal family and mark requirements as provisional.

## Operating Procedure

### 1. Orient

Identify the manuscript stage:

- `audit_only`: user wants diagnosis.
- `story_architecture`: user wants to decide the paper story before writing.
- `journal_requirements`: user wants target-journal requirements or template guidance.
- `manuscript_drafting`: user wants new manuscript text from evidence or a locked story.
- `section_revision`: user provided a section.
- `full_manuscript_revision`: user provided a full draft.
- `review_cycle`: user wants editor/reviewer simulation.
- `response_revision`: user has real reviewer comments.

State the stage briefly, then proceed.

### 2. Read References

Load only the references needed for the task:

- Story/package and claim control: `references/story-package-schema.md`, `references/claim-evidence-ladder.md`.
- Story design: `references/story-architecture-protocol.md`.
- Target journal requirements: `references/target-journal-requirements.md`.
- Manuscript drafting: `references/manuscript-drafting-protocol.md`.
- Live expression checking: `references/live-literature-expression-audit.md`.
- Logic repair: `references/logic-link-audit.md`.
- AI-style cleanup: `references/anti-ai-style-rules.md`.
- Multi-agent review: `references/multi-round-review-protocol.md`.
- Review tracking: `references/review-action-matrix-schema.md`.

### 3. Build Or Rebuild The Story

When there is no locked story package, build one before drafting:

- extract evidence and claim candidates from user materials
- propose 2-3 story options
- choose one default story and explain why the others are weaker
- define title direction, abstract logic, figure order, contribution scale, and dangerous logic jumps
- lock the story package fields

Use `references/story-architecture-protocol.md`.

### 4. Research Target Journal Requirements

Before journal-specific drafting, perform live search of official sources for target-journal requirements. Prefer official journal pages, publisher author guidelines, and official templates. Record the requirements packet and cite sources.

Use `references/target-journal-requirements.md`.

### 5. Draft Or Revise

Draft or revise only claims supported by the story package and evidence map. For new text, use the story package, live requirements packet, and live same-topic top-journal expression audit before writing. Do not draft first and search later.

Use restrained top-journal prose:

- Prefer concrete nouns, defined baselines, and measured outcomes.
- Use mechanism language only when the evidence ladder supports it.
- Replace broad novelty claims with the precise design advance.
- Keep scope narrower than the evidence.
- Make every paragraph serve a function: `context`, `gap`, `move`, `evidence`, `mechanism`, `scope`, or `implication`.
- Follow target journal requirements for abstract length, title length, display items, and section structure.

Use `references/manuscript-drafting-protocol.md`.

### 6. Run Quality Gates

After each writing pass, output a compact `quality_gate_report` with:

- `literature_expression_audit`: phrases searched, top-journal patterns found, adopted revisions (omit on light-gate passes).
- `anti_ai_audit`: deleted or rewritten AI-like patterns.
- `logic_link_map`: repaired links at points of `unsupported_jump` / `unsupported_shift` (not a per-sentence tag dump).
- `claim_safety`: any downgraded claims and why.

Then provide the revised text. A gate passes only if the manuscript text has been revised accordingly — a checklist without edited prose is a failure.

### 7. Handling Editor Pass

When the user requests a review cycle, first simulate one handling editor. Use subagents when available; do not merely role-play inside one response unless subagents are unavailable.

The handling editor checks:

- journal fit and desk-reject risk
- novelty and general significance
- fatal evidence gaps
- overclaim risk
- whether the paper deserves external review

Convert the editor output into a `review_action_matrix`, then revise immediately.

### 8. Three Reviewer Rounds

Run exactly three rounds. Each round contains three independent reviewers:

- **Reviewer A, Methods and Evidence**: evidence ladder, controls, baselines, statistics, methods, reproducibility.
- **Reviewer B, Field and Novelty**: literature positioning, novelty, target-journal fit, contribution level.
- **Reviewer C, Logic and Style**: prose, AI-like texture, paragraph flow, sentence logic, figure-to-text coherence.

Within each round:

1. Send the same current manuscript, story package, target journal profile, and previous action matrix to all three reviewers.
2. Collect comments independently.
3. Merge comments into a single `review_action_matrix`.
4. Revise the manuscript immediately.
5. Re-run all three quality gates.
6. Carry unresolved items into the next round.

Do not let reviewers silently rewrite the story. If they request a new story, mark it as `requires_story_rebuild`.

### 9. Final Output

Return:

- locked `story_package` when story design or drafting was performed
- `target_journal_requirements` when a journal was named
- drafted or revised manuscript text
- final revised manuscript or section
- concise editor verdict
- three-round reviewer history
- final `review_action_matrix`
- final `quality_gate_report`
- unresolved risk register

If evidence gaps cannot be solved by writing, say so directly and provide the narrowed claim language.

## Output Defaults

- Analysis and audit reports: Chinese.
- Manuscript prose: English unless the user asks otherwise.
- Tables: Markdown.
- Source attribution for live literature search: include links or bibliographic identifiers when available.

## Hard Prohibitions

- Do not invent data, experiments, characterization, citations, or reviewer identities.
- Do not quote long passages from papers; use short phrases only when needed and otherwise paraphrase patterns.
- Do not use smooth transitions to hide missing evidence.
- Do not preserve a stylish sentence if its logic is false.
- Do not promote correlation to mechanism or scope.
