# Reading CohortCert

Start with the Abstract, Introduction and Figure 1. Section II introduces the task before its notation: a record is a comment, a label says whether a property is present, and a cohort is a group chosen from known metadata. The question concerns the fraction of positive labels in each group. One request can require several answers.

## Follow one example

A has 100 comments and B has 80; 20 belong to both. The disjoint groups are A-only, the intersection, and B-only. Their positive counts K1, K2 and K3 give a rate difference K1/100 - K2/400 - K3/80. The intersection coefficient is negative because the same positive comment raises the smaller group's rate more.

Ranges [40,48], [8,12] and [20,24] imply a difference [0.07,0.21]. Thus difference > 0.05 is true, difference < 0.06 is false, and abs(difference) < 0.10 is unresolved. The request remains incomplete because it needs all three answers. These are illustrative values, not measured read savings.

## Read the method in execution order

| Location | Reader question | Meaning of the formal term |
|---|---|---|
| II-A/B | What goes in and what comes out? | Fixed records and groups; true/false/unresolved answers and charged reads |
| II-C | How is a label reused? | A cell groups records with the same contribution to every comparison |
| II-D | How do comparisons make an answer? | An atom is one comparison; a witness is a complete route to a true decision |
| II-E | Why can the system repeatedly check? | A confidence sequence covers fixed positive counts throughout sampling |
| III-A / Algorithm 1 | What happens after each batch? | Check evidence, decide whether to stop, select the next cell and update counts |
| III-B/C | What does each policy choose? | The policies choose reads; Forecast's predictions never justify outputs |
| III-D | What does hindsight diagnose? | Possible completion, a cost barrier, or an undecided bracket on fixed paths |
| III-E | How is completion represented? | Choose a read option per cell, require evidence, then assemble every answer |
| III-F | How are bounds checked? | Exact rational lower checks and integer feasible-allocation checks |

The offline evaluator sees future paths; the online policies do not. At a budget of 100 reads, a checked completion costing 95 proves possibility, a lower bound of 105 rules it out under the checker, and [80,110] settles neither. All total costs include the pilot. A hindsight proof is not an online allocation strategy.

## Understand the experiment units first

Section IV explains what each dataset row and label mean before introducing parameters. Table II separates studies and cost units. Table III explains comparison, equivalence, dominance, mixed and ranking requests. A saved-label replay reveals stored labels on demand; it is not a fresh model call. MAST reveals 14 flags with one record read. The live study measures actual model forwards, tokens and time separately.

Section V asks, in order, whether read selection helps, why multi-decision requests differ, whether incomplete requests could have finished, what semantic-label differences change, how forecasts behave, and what the smaller diagnostic/runtime studies show. Table IV gives primary outcomes; Table V partitions offline cases; Tables VI-VIII concern different label/inference/cost units. The full detailed result account is retained in TC5.

Figure 3 uses 4,640 primary nonranking executions per curve. Figure 4 plots finite coordinates while retaining the no-proof case in the stated denominator. Figure 5's lower completion edge counts constructed proofs; the upper edge includes cases not excluded by cost bounds. These hindsight effects are separate from measured online completion gains.

For exact statistical formulas read TC1; for complete program, dual-bound checks and the scoped mathematical construction read TC2; for exact settings and scores read TC3; for supplemental audits read TC4. README.md locates executable analysis, original sources, dependencies and external-input requirements. PAPER_ARTIFACT_BINDING.json fixes the manuscript and evidence identities.
