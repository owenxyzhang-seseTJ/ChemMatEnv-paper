# Logic-Link Audit

Use this audit to make prose logically defensible. The goal is to find and repair broken links, not to tag every well-behaved sentence.

## How To Audit

Do **not** produce a per-sentence relation tag for the whole manuscript — that yields a large, low-information table and wastes effort on sentences that already follow clearly. Instead:

1. Scan sentence-to-sentence and paragraph-to-paragraph transitions.
2. Only record an entry when a relation is **unclear, missing, or indefensible** (`unsupported_jump` / `unsupported_shift`) or when a link is repaired.
3. Well-behaved transitions need no entry.

This keeps the output focused on actual defects.

## Sentence Relations

When a sentence-to-sentence link is problematic, identify which relation is missing or broken:

- `elaboration`: adds detail to the prior sentence.
- `evidence`: supports the prior claim with data or observation.
- `contrast`: narrows or challenges the prior statement.
- `cause`: explains **why** the prior statement occurs.
- `consequence`: states **what follows from** the prior statement.
- `boundary`: limits the scope of the prior statement.
- `transition`: moves to the next necessary topic.
- `unsupported_jump`: no defensible relation.

`cause` and `consequence` point in opposite directions and are the most commonly confused:

- cause: "The framework polarizes under field X. **This polarization arises because** the linkers lack rotational freedom." (explains why the first thing happens)
- consequence: "The framework polarizes under field X. **As a result**, the selectivity inverts above 0.5 V." (states what follows from it)

## Paragraph Relations

When a paragraph-to-paragraph link is problematic, identify the relation:

- `narrowing`: broad problem to specific bottleneck.
- `precedent_limit`: prior work to the unresolved constraint it leaves behind.
- `design_response`: bottleneck to the design principle that answers it.
- `evidence_step`: claim to the figure/data that tests it.
- `mechanism_step`: observation to mechanistic interpretation.
- `scope_step`: established mechanism to its boundary or generality.
- `unsupported_shift`: topic changes without a bridge.

`precedent_limit` vs `boundary` distinction: `precedent_limit` is a transition between paragraphs — "prior work got this far, but here is the constraint it did not break." `boundary` is a within-paragraph scope qualifier on a single claim — "this holds under condition Y, not generally." Mixing them up hides a gap (a missing paragraph bridge) as if it were a hedge.

## Repair Moves

- Add a baseline or condition.
- Insert a bridge sentence that states why the next point follows.
- Move mechanism language after the evidence that supports it.
- Split a paragraph with two unrelated jobs.
- Delete a sentence whose role cannot be defended — but try repair before deletion, since deletion can drop a needed claim.

## Output

A compact table, only for repaired or flagged links:

| Location | Relation | Problem | Repair |
| --- | --- | --- | --- |
