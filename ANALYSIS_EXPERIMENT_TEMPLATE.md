# Analysis / Experiment Contract

This optional template is for work whose analysis or experiment identity, inference, comparison, or consequential interpretation warrants a durable contract. Do not use it for trivial exploration merely because it exists. Omit unused fields. A formal statistical null hypothesis is not mandatory.

## Identity and purpose

**Experiment / analysis ID:**

**Status:** `proposed | active | completed | negative | inconclusive | superseded`

**Question:**

**Scientific objective:**

**Decision this work will inform:**

## Design

**Experimental unit / unit of analysis:**

**Sampling / replicate structure:**

**Primary estimand:**

**Primary outcome / metric / feature:**

**Scientific hypothesis:**

**Statistical H0/H1:** Use only when inferential testing is justified by the design. Do not invent H0/H1 before the independent experimental unit is known.

**Alternative hypotheses / nuisance explanations / confounders:**

**Comparator / control:**

## Identities and policies

**Input dataset identity:**

**Code/configuration identity:**

**Environment identity where consequential:**

**Preprocessing:**

**Missing-data policy:**

**Exclusion policy:**

## Analysis and criteria

**Primary analysis:**

**Predeclared decision / acceptance criterion:**

**Sensitivity / robustness analyses:**

**Negative controls / sanity checks when appropriate:**

## Interpretation boundaries

**Interpretation if supportive:**

**Interpretation if negative:**

**Interpretation if inconclusive:**

**Allowed claim if successful:**

**Explicitly prohibited overclaim:**

## Outcome

**Results:**

**Limitations:**

**Decision:**

**Next discriminating experiment / analysis:**

## Lineage

Maintain the consequential chain:

`question -> analysis/experiment plan -> code/config/data identity -> run -> output/manifest -> result -> decision -> claim or next experiment`

Do not manually duplicate hashes already owned by a generated run manifest. This contract does not require one Git branch per experiment, and trivial work does not require an experiment ID.
