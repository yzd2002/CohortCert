# Reading CohortCert

The current abstract first explains the task, obstacle, insight and method. Start with the main paper's Introduction, Figure 1 and Section II. The same example is used throughout the explanation.

## One request, three questions

Cohort A has 100 records; B has 80; 20 belong to both. Let K1 count positive labels only in A, K2 in their intersection and K3 only in B. Their rate difference is `K1/100 - K2/400 - K3/80`. The overlap coefficient is negative because a positive record changes the smaller cohort's rate more.

Count ranges `[40,48]`, `[8,12]` and `[20,24]` imply a difference `[0.07,0.21]`. Thus `difference > 0.05` is true, `difference < 0.06` is false and `abs(difference) < 0.10` is unresolved. All three belong to one request: a true/false answer to one item does not complete the other items. These numbers are a schematic example, not measured acquisition savings.

## Formula decoder

| Object | Meaning | Main section |
|---|---|---|
| Cell | Records with the same contribution to every requested contrast | II-B |
| Count interval | An anytime range for a cell's fixed positive count | II-D |
| Atom | One strict threshold inequality | II-C |
| Witness | Enough atom assertions to prove a decision true | II-C |
| Decision certificate | Supported assertions giving the requested true/false values or selected set | II-C |
| Completion program | Chooses one read prefix per cell and enough assertions to finish all items | III-A/B |
| Checked cost bounds | A feasible proof gives an upper cost; a rational bound rules out all cheaper proofs | III-C |

A true decision needs one complete positive witness; a false decision must block every such witness. Strict top-k selects a set of exactly k cohorts and proves all cross-boundary comparisons. It need not order selected members internally.

## Online output and offline cost are different

The online executor uses observed labels only. All its policies share a checker and confidence procedure. Forecast's hypothetical intervals schedule reads but never justify output. DifficultyGreedy scores progress across unresolved decisions; on a single comparison its ordering reduces to width allocation in exact arithmetic.

The offline evaluator sees realized future paths under fixed inference rules and rejects selected atom assertions inconsistent with the full reference. For a budget of 100 reads, a checked completing allocation at 95 proves possibility; a lower bound of 105 rules it out; bounds [80,110] settle neither. Bounds include the pilot. This diagnosis does not itself supply an attainable causal policy.

## Read the results on their own units

Section IV and Table III map the studies. Main replays charge one record-predicate label attempt; these are not fresh model forwards. MAST charges one record revealing all 14 released flags. Live executions measure actual forwards, formatted tokens and wall time separately.

CivilComments gains over WidthGreedy are 0.78 and 1.16 percentage points for crowd and model labels; GoEmotions nearly ties. The 157/192 within-budget offline proofs and 30/192 signed-overlap cost effects are separate hindsight diagnostics. They are not online completion improvements. A sampling guarantee for fixed model labels does not establish semantic agreement with crowd annotations.

For full predictive-mixture formulas, score definitions, execution parameters and the scoped mathematical construction, read the separate Technical Companion. For executable analysis, source locations and external data/model requirements, follow README.md. The public file binding fixes the exact manuscript and evidence bytes.

The predictive proxy adds 20 pseudo-observations to Beta(1,1), so its total concentration is 22; this clarifies the frozen parameterization. Figure 3 uses 4,640 primary nonranking executions per curve. Figure 4 has finite scatter coordinates only; the no-proof case stays in the declared denominator. Figure 5's lower completion edge counts constructed proofs, and its upper edge includes cases not excluded by cost bounds.
