# Empirics - clinical trials analysis

What do we need to find?

- For H2 we need to find that post-2008 tenofovir is chosen more as a complement in add-on trials (Post2008#Tenofovir>0).
Note: this should be for firms OTHER than Gilead (tenofovir owner)

- For H3/4 (about Gilead and ViiV strategy) we need to find that post-2008 both do more trials in add-on drugs rather than base drug; and that Gilead does trials on fixed combination pill. Post2008#AddOnTrial>0; Post2008#SinglePill>0 for Gilead.
Note: for these hypotheses it is less clear: an alternative would be to 

## Endogeneity issues 

1) Phase III trial: decision is conditional on prior success of the given drug in a phase II trial, or the drug being successfully on the market

2) Choice of base vs. add-on as the main drug of the trial: conditional on the firm having base (or add-on) in its portfolio, and its success in the previous phase trial (see 1)

3) Non-industry sponsored trials can be substitutes for industry trials: I should probably include them. This will still leave the endogeneity issue of 1) and 2)

4) If I am very picky, there are also vaccines trials which may be viewed as a substitute for drug trials. 

## Potential design 1:

A panel of combinations across years that are at risk of being in a trial. E.g., "Tenofovir+Atazanavir", "Tenofovir+Rilpivirine", etc., over the years. In terms of years: we have a lot of pre-1999 trials, so we can probably start with 1999 onward to 2017. There is some left censoring as the trials in older years do not appear systematically (e.g., some combinations may have never been tried in our sample because they have all been tried before 1999). There are 34 industry trials w/o startyear (presumably before 1999), 2 trials before 1999 (1996, and 1997), and 8 trials in 1999. The remaining 190 are after 1999. 

The DV can either be binary (whether a given combination was a part of at least one trial or not in a given year) - then this is a logit. Or it can be the number of trials in a given year - then it is Poisson or negative binomial regression. 

The independent variables: 
- Tenofovir, abacavir, zidovudine indicators (somewhat similar to the analysis of consumption)
- Indicator for the same firm owning the base and the add-on (TBD)
- Trial type - base or add-on. 
- UniqueComplement indicator equal to 1 if only one complement is used in a trial. However, this can be problematic as it makes sense for trials of add-on drugs. 

### What are the issues?
- the set of combinations considered! 
    - In particular, what if there are drugs that eventually were not approved? Should we consider all possible combinations that these drugs could form? Should they be excluded from the set? 
    - linked to this: many add-on trials on pre-treated patients do not specify the base (because the patient switches from the add-on drug but can keep the base). In such case, should we consider all combinations with a given the add-on drug as being tried? 
    - Some trials explore drugs as bitherapy or monotherapy. How should these be coded? because if we rely on what was eventually tested there is a selection issue. 
- Some combinations can be like "Lopinavir+Didanosine+Stavudine". Both Didanosine and Stavudine are base drugs; yet I normally consider them as Base1 (as opposed to emtricitabine and lamivudine that are Base2). Should in this case we consider both combinations, Lopinavir+Didanosine and Lopinavir+Stavudine as being tested? Medically, I am not sure this is right. 
- We lose the by-trial information, in particular who was the sponsor, which patients (naive or pre-treated); and whether the focus of the trial was the base of the add-on. 

### First stage needed? 

To deal with endogeneity issues 1) and 2) it may be necessary to collect the data on phase 2 trials... 

## Potential design 2:
