# Multi-Round Review Protocol

Detail for the editor pass and three-round, three-reviewer cycle defined in SKILL.md (steps 7-9). Roles and the round-by-round sequence are not repeated here — this file covers only the parts SKILL.md does not: reviewer output format, subagent data-handling, and stop conditions.

## Subagent Rule

Use real subagents when available. Give each subagent only the current manuscript, story package, target journal profile, and prior action matrix. Do not provide your expected answer to the subagent.

Why: feeding the expected verdict leaks the conclusion and makes the "independent reviewer" role-play collapse into confirmation. Reviewers earn their value by surfacing objections you did not anticipate.

If subagents are unavailable, simulate roles in separate sections and keep reviewer comments independent — do not let one reviewer's framing bleed into the next.

## Reviewer Output

Each reviewer must provide:

- overall recommendation: `accept after minor revision`, `major revision`, `reject/resubmit`, or `reject`.
- top 3-6 issues.
- exact manuscript locations when possible.
- required revision action.
- whether the issue is solvable by writing or requires new data.

Why 3-6: fewer than three usually means the reviewer skipped the paper; more than six usually means the reviewer is listing every nit instead of ranking. The range forces prioritization, which is what a real editor reads first.

## Stop Conditions

The loop may stop after Round 3 only after:

- all writing-solvable major comments are addressed.
- evidence gaps are downgraded or listed in the risk register.
- quality gates have passed on the final text.

Why: stopping earlier leaves major comments that a real editor would send back out; stopping later yields diminishing returns because Round 3 is acceptance-risk focused, not a new discovery pass.
