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
