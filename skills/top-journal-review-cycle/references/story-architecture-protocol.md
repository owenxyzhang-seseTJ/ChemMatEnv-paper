# Story Architecture Protocol

Use this protocol before drafting a new manuscript or rebuilding a weak draft.

## Goal

Convert evidence into a manuscript-level story package. The question is not "how to polish this text"; it is "what story can this evidence support for the target journal".

## Inputs

- Evidence summary, data tables, figures, figure legends, slides, draft text, or author notes.
- Target journal or journal family when available.
- Known limitations, missing controls, or mechanism uncertainty.

## Procedure

1. Extract 3-5 core observations and mark each as observation, interpretation, or unsupported claim.
2. Place each candidate claim on the claim-evidence ladder.
3. Identify the field-level problem in application language.
4. Narrow it to one specific bottleneck or unresolved tradeoff.
5. Define the design principle as the answer to that bottleneck.
6. Propose 2-3 candidate stories, then choose one default story.
7. Explain why the weaker stories are weaker: insufficient evidence, weaker novelty, poor journal fit, scattered contribution, or overclaim risk.
8. Design title direction, abstract logic, figure order, and target-journal positioning.

## Story Package Output

The narrative fields below are the design artifacts of story architecture; the locked `story_package` schema (8 required fields) that downstream drafting depends on is defined in `story-package-schema.md`. Both are produced together — the narrative fields explain the story, the schema fields constrain it.

Return:

- `one_sentence_story`
- `paper_narrative_spine`: broad challenge -> sharp bottleneck -> constrained prior routes -> design principle -> evidence chain -> implication
- `candidate_stories`: 2-3 options with strengths and weaknesses
- `selected_story`: default option and rationale
- `title_directions`: 2-3 candidate titles adjusted to journal level
- `abstract_logic`: sentence-level or paragraph-level summary logic
- `figure_logic`: figure order and the manuscript question each figure answers
- `dangerous_logic_jumps`: claims most likely to be attacked
- `target_journal_positioning`: contribution level and realistic journal fit
- `story_package`: the locked schema from `story-package-schema.md`

## Rules

- Start from a field-level bottleneck, not from the material class alone.
- Keep one headline contribution. Other results support it.
- A design principle must answer the bottleneck, not merely describe synthesis.
- Do not use language to raise a claim above its evidence rung.
- For Nature or Science family targets, state the generalizable insight. For specialist journals, emphasize technical depth, mechanism, and benchmark relevance.

