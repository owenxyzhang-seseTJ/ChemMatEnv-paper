# Live Literature Expression Audit

Use this protocol before drafting and whenever text sounds translated, awkward, too generic, or inconsistent with target-journal prose.

## Source Priority

1. Same-topic papers in the target journal, same article type, recent papers.
2. Same-topic papers in the same publisher family or adjacent top journals.
3. Field-specific high-impact journals in the same topic area.
4. User-provided same-topic top-journal papers only if live search is unavailable.

Why this order: phrasing conventions are journal- and article-type-specific (a Nature Letter abstract does not read like a JACS Communication). Closer matches on journal, topic, and article type give patterns that will actually fit the target venue; broader sources are a fallback when closer ones are thin.

## Search Pattern

Search for combinations of:

- target journal name
- material class or process
- section type: abstract, introduction, results, conclusion
- core concept: selectivity, flux, active site, pore confinement, charge transfer, stability, uptake, catalysis
- candidate phrase or verb that may be awkward
- same-topic benchmark terms, such as MOF, COF, membrane, adsorption, electrocatalysis, photocatalysis, ion transport, defect, confinement, interface, or stability

## Audit Table

Use this table:

| Original expression | Concern | Search query | Top-journal pattern | Source | Adopted revision |
| --- | --- | --- | --- | --- | --- |

Keep source notes short. Do not reproduce long copyrighted passages.

## What To Learn

- Verb choice: `show`, `demonstrate`, `reveal`, `indicate`, `support`, `establish`.
- Hedge strength: `can`, `may`, `could`, `is consistent with`, `suggests`.
- Collocation: use the noun and verb pair that appears natural in the field.
- Discourse move: how the paper frames gap, design principle, evidence, mechanism, and implication.
- Section convention: how same-topic papers open abstracts, introduce bottlenecks, start results subsections, and close implications.

## What Not To Do

- Do not copy sentences.
- Do not force a Nature-style phrase into a JACS-style paper if the article type differs.
- Do not replace clear technical prose with fashionable but vague language.
- Do not let literature phrasing override the evidence ladder.
- Do not use off-topic papers as phrase evidence when same-topic sources are available.

## Per-Journal Diction Calibration

When the target journal is known, calibrate diction empirically by sampling recent same-topic articles from that journal. This goes beyond generic expression search — it tunes the voice to what that specific journal actually publishes. Adapted from the nature-polishing skill's diction calibration method.

### Calibration Method

1. **Sample ~20 recent articles** from the target journal in the same topic area and article type.
2. **Count connector frequencies**: record every `However`, `Furthermore`, `Moreover`, `In contrast`, `Nonetheless`, `Indeed` and compute ratios. Example from a NatComms 2025 corpus: However 51 >> Furthermore 22. If a journal uses `Interestingly` 0 times, do not use it.
3. **Check `significantly` occurrence**: count every instance and verify whether each is backed by a statistical test. In many top journals, `significantly` appears 0 times outside explicit statistics — if the draft uses it casually, remove or back it.
4. **Map hedge concentration**: hedge phrases (`may`, `could`, `suggests`, `is consistent with`) should cluster in the Discussion and Conclusion, not in the Results. If the target journal's Results sections use almost no hedging, match that.
5. **Rank achievement verbs by frequency**: from strong to weak — `demonstrate`, `achieve`, `outperform`, `show`, `compare favorably`, `reach`, `match`, `approach`. Calibrate the draft's verb choices to the journal's observed distribution.
6. **Record tense and voice conventions**: past tense vs. present perfect in abstracts? Active vs. passive in Methods? Adjust to match.

### Journal-Specific Observations

- **ACS journals** (JACS, ACS Nano, Nano Lett.): prefer active voice in Results and Discussion; supplementary carries full experimental detail; abstracts are tightly worded (waste no words on background the title already gives).
- **RSC journals** (EES, Chem. Sci., J. Mater. Chem. A): tolerate moderate editorial language (`interestingly`, `notably` appear); Methods sections tend to be more compact than ACS equivalents; RSC house style uses [1] superscript citations.
- **Wiley journals** (Angewandte, Adv. Mater.): allow longer compound sentences; titles often declarative or colon-separated; figures emphasized (10+ in a full paper); Angewandte reports shorter and more urgent than Adv. Mater.
- **Nature journals**: no em dashes in prose; hedging calibrated (neither overclaim nor timid); broad-audience opener required for Nature proper; Methods at end for Nature/Nature subjournals, inline for NatComms.
- **Science / Science Advances**: similar to Nature in audience breadth; Reports format is shorter and punchier than NatComms Articles; summary required.

### Calibration Output

After sampling, produce a short `diction_profile` with:
- top 5 connectors by frequency
- `significantly` count and context
- hedge distribution (Results vs. Discussion)
- achievement verb ranking
- any journal-specific quirks (e.g., "this journal never uses `first-ever`" or "this journal allows `delve` only in Perspectives")

