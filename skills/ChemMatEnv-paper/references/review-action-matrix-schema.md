# Review Action Matrix Schema

Use this matrix to convert editor and reviewer comments into concrete revisions.

| ID | Source | Severity | Location | Comment | Action | Text changed? | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |

## Field Rules

- `ID`: stable id such as `E1`, `R1A-2`, `R3C-4`.
- `Source`: handling editor, reviewer A/B/C, or quality gate.
- `Severity`: `fatal`, `major`, `minor`, `style`.
- `Location`: section, paragraph, sentence, figure, or claim.
- `Comment`: the critique in one concrete sentence.
- `Action`: revise, downgrade, delete, move, add bridge, add citation, request data, or mark risk.
- `Text changed?`: yes/no, with a short note.
- `Status`: resolved, partially resolved, unresolved-data-needed, rejected-with-reason.

## Rules

- Every major or fatal item must either change the text or be placed in the final risk register.
- Do not mark an item resolved because the prose sounds better.
- If the reviewer asks for evidence not present in the user materials, downgrade the claim or mark data needed.
- Carry unresolved items into the next reviewer round.

