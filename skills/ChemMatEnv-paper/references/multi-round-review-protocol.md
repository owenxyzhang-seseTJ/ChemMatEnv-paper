# Multi-Round Review Protocol

Detail for the editor pass and three-round, three-reviewer cycle defined in SKILL.md (steps 7-9). This file covers reviewer output format, **hard subagent dispatch rules**, data isolation, and stop conditions.

## Hard Subagent Dispatch Rules

**MUST dispatch real subagents for every reviewer in every round.** This is not optional:

1. **Handling editor** = one subagent (before Round 1)
2. **Three reviewers** = three subagents per round × 3 rounds = 9 subagent calls total
3. **Revision editor** = one subagent per round (after merging)

**Parallel dispatch:** If your platform supports concurrent subagents, dispatch all three reviewers in parallel within each round. Reviewers are independent — they do not wait for each other.

**Temperature:** Use nonzero temperature (0.3–0.5) for all reviewer subagents. Zero-temperature reviewers produce formulaic, sycophantic output that collapses independence.

**Input isolation — what each reviewer subagent receives:**
- ✅ Current manuscript (same version for all three)
- ✅ Locked story package
- ✅ Target journal profile
- ✅ Prior round's `review_action_matrix` (Rounds 2 & 3 only)
- ✅ Their own agent definition file (from `agents/`)

**Input isolation — what each reviewer subagent MUST NOT receive:**
- ❌ Other reviewers' comments from the same round
- ❌ Your opinion, expected verdict, or leading questions
- ❌ The editor's comments
- ❌ Any "here's what I think the problems are" preamble

**Why this matters:** The value of three reviewers is NOT that they produce more text — it is that they surface objections you did not anticipate. If reviewer B sees reviewer A's comments before writing, you get three variations on the same theme, not three independent perspectives. Feeding the expected verdict ("please check if the overclaim in paragraph 3 is an issue") leaks the conclusion and collapses the review into confirmation.

**If subagents are genuinely unavailable:**
- Run each reviewer in a completely separate message/turn
- Use nonzero temperature
- Declare `⚠️ SUBAGENT_UNAVAILABLE: ROUND N simulated`
- Explain what was lost (independent judgment, parallel discovery)
- Still enforce input isolation: do not carry reviewer A's framing into reviewer B's session

## Revision Editor Dispatch

After merging the action matrix, dispatch a revision editor subagent (`agents/revision-editor.md`). Pass it ONLY:
- The merged `review_action_matrix` (not individual reviewer outputs)
- The current manuscript text
- The story package (to prevent silent story drift)

The revision editor revises and returns the updated manuscript. Then re-run quality gates.

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
