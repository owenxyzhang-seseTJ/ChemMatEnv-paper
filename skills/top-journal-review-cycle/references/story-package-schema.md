# Story Package Schema

Field definitions for the story package. The required field list and the locking rule (core problem, bottleneck, design principle, and main claims cannot change without an explicit rebuild) live in SKILL.md; this file gives each field's meaning and the red flags that signal a story is drifting from its evidence.

## Field Definitions

- `core_problem`: field-level problem in application language (not "we made material X").
- `specific_bottleneck`: the precise unresolved tradeoff, mechanism gap, or control problem this work attacks — narrow enough that the evidence can actually address it.
- `design_principle`: how the work addresses the bottleneck; the transferable idea, not just the recipe.
- `main_claims`: ranked claims, strongest first, so reviewers can see what is load-bearing.
- `evidence_map`: figure/data-to-claim mapping with named baselines and conditions — claims without a mapped figure are unfounded.
- `mechanism_position`: what is proven, what is suggested, and what must stay correlation-level (aligns with `claim-evidence-ladder.md`).
- `scope_limits`: materials, substrates, conditions, and generality boundaries — the honest edge of what was tested.
- `target_journal_profile`: target journal, article type, word/figure limits, and the expected contribution level at that venue.

## Red Flags

- A title claims scope broader than tested systems. Why: scope broader than the evidence is the most common desk-reject trigger and the hardest to defend in revision.
- A mechanism claim lacks independent evidence. Why: a single correlative observation cannot anchor a mechanistic claim; reviewers at top journals treat this as overclaim.
- A paragraph moves from performance to a general design rule without a bridge. Why: jumping from one result to a universal rule skips the step that would make the rule defensible, and reads as overreach.
- The manuscript claims a field-level advance but only compares against weak or unnamed baselines. Why: the contribution level is defined by the comparator; a weak baseline inflates the advance and collapses under review.
