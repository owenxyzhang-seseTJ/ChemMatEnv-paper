# Anti-AI Style Rules

AI-like writing is usually over-smooth, over-broad, and weakly evidenced: it sounds confident while substituting praise and template moves for specific data, baselines, and causal links. The fixes below are not about banning words — they are about replacing empty rhetoric with the evidence it is standing in for.

## Blocked Patterns

- Generic novelty praise without data or comparison.
  - AI-like: "This work presents a groundbreaking and efficient catalyst."
  - Better: "The catalyst reaches a turnover frequency of 1.2×10⁴ h⁻¹ at 80 °C, exceeding the Pt/C baseline (3.1×10³ h⁻¹) under the same feed."
- Repeated paragraph shape: `background -> gap -> solution -> significance` in every paragraph. Vary the shape so each paragraph does a different job (evidence, mechanism, boundary, implication).
- Repeated sentence shells across adjacent paragraphs (e.g., starting three paragraphs with "Notably, ...").
- `Moreover / furthermore / notably` chains that do not encode real logic — they assert connection without stating the relation (contrast, cause, evidence, boundary, or consequence).
- Inflated ending sentences that could fit any materials paper.
- Mechanism claims before the evidence ladder is complete (see `claim-evidence-ladder.md`).

## Delete Or Replace

Each word below is a flag, not an automatic delete. The rule is the boundary, not the word:

- `delve` — almost always replace; it decorates analysis instead of doing it. Use a concrete verb ("we analyze", "we measure").
- `landscape` — replace with the specific field, system class, or literature set you actually mean.
- `multifaceted` — replace by naming the facets; if you cannot, the sentence is too vague.
- `notably` (emphasis-only) — delete; if the point matters, the data should make it matter.
- `crucial` without a measured consequence — keep only when you state what breaks without it.
- `comprehensive` without defined coverage — keep only when you enumerate what was covered.
- `leverage` as a dressed-up `use` — use `use`, or specify the mechanism being leveraged.
- `robust` outside statistical or mechanical robustness — keep only with a metric or stress test.
- `pivotal` / `groundbreaking` — keep only for a result that actually reorders the field, and then back it with a comparator; otherwise it reads as marketing.
- `shed light on` — replace with the specific thing now understood and the evidence for it.
- `pave the way` — replace with the concrete next step or capability it enables.

## Rewrite Rules

- Replace praise with metric, condition, and comparator.
- Replace vague transitions with the actual relation: contrast, cause, evidence, boundary, or consequence.
- Split long symmetrical sentences when clauses repeat the same function.
- Keep the strongest sentence only when two sentences make the same move.
- Give abstract and conclusion different sentence architecture — the abstract states the result; the conclusion states the scope and what is now possible, so they should not be paraphrases.

## Chinese-to-English Repair Patterns

When the source is a Chinese academic draft, fix these patterns before sentence-level polishing. These are language-structural, not field-specific, but they are pervasive in Chinese-authored materials/chemistry papers.

### 8 Common Repair Patterns

1. **Broad importance before a clear object.** Chinese drafts often open with "X is an important class of materials with wide applications" before naming what X is. Move the specific object before the importance claim.
2. **Method list before the research gap.** Chinese drafts often enumerate synthesis methods or characterization techniques before stating the bottleneck they address. State the gap first, then explain how the methods test it.
3. **`显著提高` / `明显改善` without a baseline.** "Catalytic activity was significantly improved" — compared to what? Under what conditions? Replace with a metric, a named baseline, and the conditions: "The catalyst reached a turnover frequency of 1.2×10⁴ h⁻¹ at 80 °C, exceeding the Pt/C baseline (3.1×10³ h⁻¹)."
4. **`首次` / `创新性` without scope.** "This is the first report of X" — first under what conditions? In what material class? State the boundary explicitly or narrow the claim.
5. **Mechanism inferred from correlation.** Chinese drafts commonly move from characterization data (XRD peak at X°, XPS binding energy at Y eV) directly to a mechanism claim without a falsification path. Downgrade to "is consistent with" or add the control experiment that would rule out the alternative.
6. **Results and implications mixed in the same paragraph.** Separate observation from interpretation. Results paragraphs stay in past tense with declarative syntax; Discussion paragraphs interpret with hedging.
7. **Topic nouns repeated where English uses pronouns or omission.** Chinese tolerates repetition of "the catalyst," "the material," "the framework" in every sentence. In English, use pronouns, definite noun phrases, or zero-connective progression once the topic is established.
8. **Comma-joined short clauses instead of explicit connectives.** Chinese academic prose often chains observations with commas. In English, split or add explicit relations: contrast, cause, consequence, boundary, or refinement.

### Translation Workflow

1. Extract core propositions in plain English before drafting polished prose.
2. Reconstruct explicit logical links (contrast, cause, implication, limitation) that the Chinese source elides.
3. Verify terminology, causality, and hedging strength against the evidence.
4. Keep technical terms (material names, characterization abbreviations, IUPAC names, statistical terms) stable across sections.
5. Apply English sentence and paragraph rules only after logic is rebuilt.

### Materials/Chemistry-Specific Patterns

- **`通过X表征证实了Y`** (confirmed Y by X characterization): specify which peak, signal, or lattice fringe and its assignment. "XRD confirmed the crystalline phase" is a reviewer target — state which peaks at which 2θ match which reference pattern.
- **`具有良好的性能`** (has good performance): replace with a specific metric and a named comparator: "reached a BET surface area of 1,200 m² g⁻¹ (N₂, 77 K), exceeding the unmodified MOF baseline (850 m² g⁻¹)."
- **`形貌/结构/组成`** (morphology/structure/composition): lock terminology on first use and enforce across all sections. TiO₂ ≠ TiO2 ≠ titania nanoparticles ≠ titanium dioxide — pick the canonical form and use it everywhere.

