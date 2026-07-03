# Failure-Mode Diagnosis

Before editing any manuscript text, diagnose structural problems first. Do not sentence-polish a draft whose section job is wrong — surface the structural problem, then fix it, then polish. Adapted from the nature-polishing skill.

## Pre-Edit Diagnostic Checklist (9 Items)

| # | Failure Mode | Check |
|---|---|---|
| 1 | **Wrong paper type logic** | Does the argument chain match the paper type (research, hypothesis, review, methods)? A methods paper structured as a research paper loses its contribution. |
| 2 | **Missing gap or poor positioning** | Is the field-level bottleneck stated explicitly? Can the reader find "what was unresolved" in the first two paragraphs? |
| 3 | **Claim without evidence** | Does every claim in the abstract, introduction, and conclusion trace to a figure, table, or data point? |
| 4 | **Evidence without a claim** | Does every figure, table, and characterization result answer a stated question? Results without a framing claim read as a data dump. |
| 5 | **Missing boundary or limitation** | Are the scope limits stated? Does the paper specify which materials, substrates, conditions, and generality boundaries apply? |
| 6 | **Results and Discussion mixed** | Are observations and interpretations in separate sections? "The XRD peak at 12.3° indicates a layered structure" mixes observation and interpretation in the same sentence — split them. |
| 7 | **Weak title or abstract signal** | Does the title encode the control lever and target outcome? Does the abstract state the bottleneck, result, and implication without hiding behind vague language? |
| 8 | **Inconsistent terminology** | Are the material name, abbreviations, units, and notation identical across all sections? TiO₂ vs TiO2 vs titania nanoparticles vs titanium dioxide — pick one and lock it. |
| 9 | **Sentence-level clutter only** | If items 1-8 are clean and only word-level issues remain, then sentence-polish. Otherwise fix structure first. |

## Priority Hierarchy

```
paper type → section job → paragraph logic → claim/evidence/boundary → sentence polish
```

Do not skip levels. A paper with a broken section job cannot be rescued by better sentences. A claim without evidence cannot be rescued by hedging. Fix at the deepest flawed level, then move down.

## Common Materials/Chemistry-Specific Failures

- **Characterization without assignment**: an XRD pattern, XPS spectrum, or TEM image is shown but the peaks, binding energies, or lattice fringes are not assigned to specific phases or planes. This is the #1 reviewer attack point in materials papers.
- **Property claim without comparator**: "exhibits high catalytic activity" — compared to what? Under what conditions? Without a named baseline, the claim is unfalsifiable.
- **Mechanism from correlation**: kinetic data, spectroscopy, or computation shows a correlation, but the paper uses `drives`, `governs`, or `enables` without ruling out alternatives. Downgrade to `is consistent with` or `suggests`.
- **Overgeneralized scope**: a single composition, single substrate, or single condition is tested, but the conclusion implies generality across a materials class. Scope must be narrower than or equal to the evidence.
- **SI as the real paper**: the main text is a highlight reel while all characterization detail lives in SI. Top journals increasingly expect key characterization (PXRD, TEM, XPS survey) in the main text, not buried in SI.
