# Empirics - clinical trials analysis

## Endogeneity issues/ 

1) Phase III trial: decision is conditional on prior success of the given drug in a phase II trial, or the drug being successfully on the market

2) Choice of base vs. add-on as the main drug of the trial: conditional on the firm having base (or add-on) in its portfolio, and its success in the previous phase trial (see 1)

3) Non-industry sponsored trials can be substitutes for industry trials: I should probably include them. This will still leave the endogeneity issue of 1) and 2)

## Potential design:

A panel of combinations across years that are at risk of being in a trial. E.g., "Tenofovir+Atazanavir", "Tenofovir+Rilpivirine", etc., over the years. In terms of years: we have a lot of pre-1999 trials, so we can probably start with 1999 onward to 2017. There is some left censoring as the trials in older years do not appear systematically (e.g., some combinations may have never been tried in our sample because they have all been tried before 1999). 

The DV can either be binary (whether a given combination was a part of trial or not)
