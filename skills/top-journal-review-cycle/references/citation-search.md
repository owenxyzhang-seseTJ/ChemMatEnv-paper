# Citation Search Protocol

Use this protocol when the user asks to add references, find supporting citations for specific claims, or build a reference list for a materials/chemistry/environment manuscript. This is a standalone capability — not a mandatory quality gate. Run it only when the user requests it or when a claim in the draft visibly lacks cited support.

## Journal Scope

Default: materials/chemistry/environment top journals. The scope can be narrowed by the user.

| Family | Representative Journals | Publisher |
|---|---|---|
| **ACS** | JACS, ACS Nano, Nano Lett., Chem. Mater., ACS Catal., ACS Energy Lett., EST, ACS Cent. Sci., Acc. Chem. Res., ACS Appl. Mater. Interfaces, Chem. Rev. | ACS Publications |
| **RSC** | EES, Chem. Sci., Mater. Horiz., J. Mater. Chem. A/B/C, Chem. Soc. Rev., Green Chem., Nanoscale, Environ. Sci.: Nano | Royal Society of Chemistry |
| **Wiley** | Angew. Chem. Int. Ed., Adv. Mater., Adv. Energy Mater., Adv. Funct. Mater., Small, Adv. Sci. | Wiley |
| **Elsevier** | Chem, Joule, Matter, Nano Today | Elsevier / Cell Press |
| **Nature family** | Nat. Mater., Nat. Chem., Nat. Energy, Nat. Nanotechnol., Nat. Sustain., Nat. Geosci., Nat. Commun., Commun. Chem., Commun. Mater., Commun. Earth Environ. | Nature Portfolio |
| **Science family** | Science, Sci. Adv. | AAAS |

Do not cite a paper merely because its title is related. Check the abstract or publisher page before presenting it as support.

## Workflow

### 1. Segment the Text

Split the user's text into citable segments at paragraph boundaries. For paragraphs with multiple claims, split at sentence boundaries. Assign stable IDs (S001, S002…). Skip section headings and connective sentences. If >10 segments, use batch mode: process in groups of 5-10.

### 2. Parse Each Segment into a Searchable Claim

For each segment, extract:
- the core claim in one sentence
- claim type: mechanism, property, synthesis, characterization, application, environmental impact, method, review, background
- the phenomenon, entity, relationship, context, and boundary

Translate Chinese claims into English concept queries, not literal translations.

### 3. Build Search Queries (Three Levels)

Use this framework adapted from the nature-citation search strategy:
- **Precise**: entity + relationship + outcome + context → exact match
- **Synonym**: alternate names, abbreviations, IUPAC-to-common mappings
- **Broad**: field-context query when no direct match appears

For materials/chemistry/environment, include material class, synthesis method, characterization technique, or property metric in the query as appropriate. Do not use overly long queries — prefer precision over volume (target 3-8 candidates per claim).

### 4. Search

Live web search via Crossref API, publisher pages, Google Scholar, or PubMed (for environmental health topics). Prefer publisher pages and structured metadata over secondary databases. Record search date for date-sensitive claims.

### 5. Evaluate Support (Conservative 5-Level Scale)

| Grade | Meaning | Use |
|---|---|---|
| **Strong support** | Directly tests same core claim in a similar material/system/condition | Experimental/mechanistic/quantitative claims |
| **Partial support** | Supports one component or narrower setting | Carefully qualified claims |
| **Background support** | Establishes field context or prior observation | Introduction/background sentences |
| **Contradictory / limiting** | Conflicts with or narrows the claim | Discussion, limitations — do not cite as support |
| **Metadata-only candidate** | Title or metadata suggests relevance; abstract not checked | Screening only — never present as support without checking |

Never present a metadata-only candidate as support. Do not cite a review as primary evidence for a mechanism claim.

### 6. Export

Default: one `.enw` (EndNote tagged) file. Optional: `.ris` or `.rdf` (Zotero). Sort by segment ID. Do not invent missing bibliographic fields — mark them as `[not found]`.

### 7. Report

Standard output template:
1. **HTML browser path first** (if visualization was generated)
2. **Scope**: which journal families and date range were searched
3. **Segment-to-reference mapping**: S001 → candidate papers with support grade and reasoning
4. **Export file path**
5. **Risks and gaps**: claims with no strong support, claims relying on reviews or metadata-only candidates, contradictory evidence found

## Common Failure Modes in Materials/Chemistry/Environment

- **Different mechanism**: the paper describes a different reaction pathway or structure-property relationship than what the claim asserts.
- **Association ≠ causality**: correlational observation presented as mechanistic proof.
- **Different material/system**: similar phenomenon but a different catalyst, framework, polymer, or environmental matrix.
- **Review used as primary evidence**: a review surveys primary work; it does not establish a new claim.
- **Claim too broad for a single citation**: "MOFs are promising for gas separation" needs a focused claim and a specific system.
- **Synthesis route differs**: the cited paper uses a different precursor, solvent, or activation protocol — the result may not generalize.

## Chinese Mode

When the user provides Chinese text or asks in Chinese:
- Accept Chinese input; search using English concept queries (translate the scientific concepts, not sentences literally).
- Return segment notes and evidence notes in Chinese by default.
- Flag support grades with Chinese labels: 强支撑 / 部分支撑 / 背景支撑 / 矛盾或局限 / 仅元数据候选.
- Preserve the exact source segment and show the English claim it was translated into.
