# Per-Section Playbooks

Section-by-section drafting rules adapted for materials, chemistry, and environment top-journal papers. Synthesized from the nature-writing and nature-polishing section fragments. Use alongside the evidence ladder (`claim-evidence-ladder.md`) and the live expression audit (`live-literature-expression-audit.md`).

## Abstract

**Default pattern:** `context/problem → gap → approach → key result → implication → boundary`

Six moves, one paragraph. The gap and contribution must each be one short, locatable sentence. Cut background the title already implies. The last sentence must state significance, not repeat the result.

**Journal-specific variants:**
- JACS / Angewandte Communications (~150 words): fuse context+gap into one sentence; lead with the finding.
- Adv. Mater. / EES Full Papers (~250 words): expand the boundary sentence to name the test conditions.
- Nature / Science: lead with a field-level sentence a non-specialist can parse; close with the generalizable insight.

**Diagnostics:** "Here, we" may signal missing context before the contribution. A broad promise without a number, comparison, or test feels ungrounded. Check: can the reader state the bottleneck and the main result after reading only the abstract?

## Introduction

**Default funnel (four paragraphs):**

1. **Field stake** — why this material, property, or environmental problem matters.
2. **Bottleneck** — what current materials or approaches do not achieve, stated as a precise unresolved tradeoff, mechanism gap, or control problem.
3. **Prior attempts** — synthesis of prior work grouped by design strategy or mechanism (not by author), each block ending with the limitation this paper addresses.
4. **This paper** — the design principle, what was demonstrated, and the roadmap of evidence to follow.

**Materials/chemistry-specific variants:**
- **Property-first**: lead with the target property and why it is hard to achieve, then narrow to the materials design challenge.
- **Design-strategy**: lead with the design rationale (e.g., "pore engineering," "defect tuning," "heteroatom doping"), then show how prior implementations of that strategy fell short.
- **Application-pull**: lead with the application need (e.g., CO₂ capture, water purification, battery longevity), then narrow to the materials bottleneck.

**Rules:**
- Do not summarize Results or Conclusion in the Introduction.
- Do not write a separate literature-catalog section — citations earn their place by defining the constraint the present design resolves.
- The transition from "what is known" to "what we do" must be explicit — not implied by paragraph ordering alone.
- Close the introduction with a roadmap so readers can predict the evidence order.

**Common failures:** textbook opening (not positioning), implied-but-unnamed gap, missing transition from prior work to this paper, excessive methods preview.

## Results and Discussion

### Results

- **Tense:** mainly past tense.
- **Openings:** claim-first — "The catalyst reached a turnover frequency of 1.2×10⁴ h⁻¹ at 80 °C" not "Figure 3 shows the catalytic performance."
- **Syntax markers:** `was detected`, `increased`, `showed`, `enabled`, `achieved` — not `may reflect`, `suggests that`, `is likely due to` (those belong in Discussion).
- **Evidence ladder for materials/chemistry papers:**

```
synthesis & characterization → primary property measurement →
comparison to named benchmarks → mechanistic/structural origin →
stability/durability tests → generalization to related systems →
boundary conditions / failure modes
```

- **Characterization discipline:** an XRD pattern, XPS spectrum, or TEM image must have peaks, binding energies, or lattice fringes assigned. "As shown in Figure 2a, the XRD pattern confirms the crystalline phase" is insufficient — state which peaks at which 2θ values correspond to which planes of which phase.
- **Property comparisons must be at equivalent conditions** (temperature, atmosphere, cycling rate, electrolyte, pH). Comparing catalytic activity measured at 80 °C to a literature value at 25 °C is a reviewer trap.

### Discussion

- **Interpret, do not re-summarize Results.** The Discussion answers "how we understand the results and when that understanding may fail."
- **Address rival explanations before generalizing.** If claiming a mechanism, explicitly name the alternative mechanism(s) the evidence rules out and why.
- **Hedging matches evidence strength.** Calibrate:
  - strong evidence + direct probe → `shows`, `demonstrates`
  - moderate evidence + one probe type → `indicates`, `supports`
  - correlational or indirect evidence → `suggests`, `is consistent with`, `may reflect`
- **Limitations come from inside the paper**, not from generic disclaimers. "Only one composition was tested" is an inside limitation; "more research is needed" is filler.
- **Sentence syntax:** `may reflect`, `suggests that`, `could indicate`, `is likely due to`, `may facilitate`.

### Per-Subsection Chain (Results paragraphs)

For each results subsection:
```
claim → figure or experiment → named comparator → mechanism or interpretation → boundary → mini-takeaway
```

The subsection opener states the claim the figure is about to prove, so the reviewer evaluates the figure against an explicit promise.

## Conclusion

**Three-part close:**
1. Restate the central contribution in one sentence.
2. Summarize the decisive evidence (what data anchors the claim).
3. State the implication with its boundary — "This design principle generalizes to [specific class] but has not been tested beyond [specific condition]."

**Overclaim check (before finalizing):**
- Does every claim in the conclusion trace to evidence in the Results?
- Are mechanism words (`drives`, `governs`) backed by the study design?
- Is the implication scope narrower than or equal to the evidence scope?
- Is "first" genuinely first, or just "first in this specific combination"?
- Does the conclusion avoid rephrasing the abstract?

No new data. No generic "more work is needed" — instead, state the specific next experiment or open question the current work makes possible.

## Title

**Default pattern (materials/chemistry):** `[System or material] + [action or capability] + [application or consequence]`

**Generate 3-5 alternatives spanning:**
- **Declarative:** "Pore-Engineered MOFs Achieve Record C₂H₂/CO₂ Selectivity via Gate-Opening Mechanism"
- **Colon-separated (JACS/Angewandte style):** "Tuning the Spin State: Single-Atom Iron Catalysts with Controllable Peroxidase-Like Activity"
- **Finding-led (Adv. Mater. style):** "A Self-Healing Ionogel with 50 MJ m⁻³ Toughness Enables Damage-Tolerant Soft Robotics"

**Rules:**
- Tell the reader what to expect — be specific enough to be searchable.
- Substantiate every quantitative word against the manuscript.
- Avoid: grant-style aims ("Toward…", "A study of…"), overbroad claims ("A new era of…"), question titles, unrecognizable jargon.
- Strip jargon the target journal's general audience would not recognize.
- Pick the most defensible title as the default.

## Paper-Type Argument Chains

### Research Paper (most common in materials/chemistry)
```
field need → specific material/target property gap → design rationale →
synthesis strategy → structural & chemical characterization →
property/performance vs. named benchmarks → mechanistic understanding →
broader implication → scope boundary
```
Drafting order: Results first → Introduction/Conclusion framed around Results → Title from strongest result + scope → Abstract last.

### Hypothesis / Mechanism Paper
```
phenomenon → candidate explanation(s) → hypothesis stated explicitly →
falsification path (what would disprove it) → evidence for/against →
rival explanations addressed → bounded conclusion
```
State hypothesis explicitly and locatably. Distinguish supporting evidence from consistent-but-non-discriminating evidence. Address rival explanations before generalizing. For chemistry mechanism papers: specify which spectroscopic or kinetic evidence distinguishes the proposed mechanism from the leading alternative.

### Methods / Technique Paper
```
task/problem → limits of existing methods → proposed method →
evaluation showing advantage (reliability, speed, cost, resolution) →
reproducibility evidence → boundary
```
For materials characterization methods: specify detection limits, reference standards, inter-laboratory reproducibility. Forbidden vague phrases: "under standard conditions," "using routine methods," "data were analyzed statistically," "the method was validated," "samples were randomly assigned."

### Review Paper
```
scope & inclusion criteria → organizing principle → synthesis grouped by
argument (mechanism, method, conclusion) → disagreements & gaps →
author's stance with reasoning → outlook with informative open questions
```
Replace "Author A reported X. Author B reported Y." with synthesis grouped by mechanism, method, or conclusion. Use logical connectives (`in contrast`, `building on this`, `the remaining disagreement is`), not generic ones (`furthermore`, `additionally`). The closing should leave a usable research map, not a summary.

### Computational / Modeling Paper
```
task definition & scope → what the model/system is → why it works
(design rationale) → how well it works (evaluation vs. experimental
reference data) → component analysis isolating contribution →
failure modes & cost characteristics → applicability boundary
```
For DFT/molecular dynamics: report functional, basis set, convergence criteria, and comparison to experimental reference. For ML potentials: report training set composition, test-set performance, and extrapolation limits.
