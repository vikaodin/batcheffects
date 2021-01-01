# batcheffects
A question that is specific to the twin design (or indeed any other design with naturally clustered observations) concerns the manner of allocation of twins to batches. One may allocate randomly by individual twin, or randomly by twin pair. The latter implies that the twin pairs share the batch, the former does not rule out batch sharing. The following are the results of simulation studies carried out to answer this question in three situations. 

Simulation 1. Random effects model. 

Simulation 2: Fixed batch effects in two steps or one step. 

Simulation 3: More extreme selection and fixed plate effects in two step or one step. 

Simulation 4: estimating genetic and non-genetic variance components in the twin design


How to allocate twins to batch in assay of metabolites in an extremely discordant and concordant (EDAC) twin design?

Discordant and concordant twin pairs are selected on the basis of a phenotypic scores, for example aggression scores, for a biomarker study. Assays on the twins' urine samples are done to measure metabolites. The aim is to determine the association between metabolite levels and aggression. The metabolites are determined on plates (i.e. in batches). The present question concerns the allocation of twins to batch, given that plate is a source of systematic variation:
1) assign twin pairs randomly to batches
2) assign twin members (individuals) randomly to batches. 
An additional question, specific to the EDAC design, is the choice of the independent variable. As the selection is on aggression scores it is statistically expedient to regress metabolite (predictor) on aggression (dependent). Selection on the predictor does not affect the regression, and if the selection is based on an EDAC scheme, the selection results in little loss of power. Alternatively one may choose to regress metabolite on the binary aggression scores (e.g., 0=low, 1=high). Regression on the continuous score is expected to confer greater power.
We make the following assumptions concerning the analysis. We assume that the twin data are to be analyzed in a single statistical model, which will include the discordant and concordant twins. With respect to this model, in testing the association of metabolite and aggression, we have to accommodate 1) the inherent two-level structure (family clustering of twins in twin pairs), and 2) the batch effects. We consider two models:
1) Linear mixed model, in which effect of batch is accommodated by means of a random effect (variance component). 
2) Fixed regression model with metabolite corrected for batch in one or two step procedure. Two step procedure: regress metabolite on plate first, use residuals in regression on predictor. One step procedure: regress metabolite on plate and on predictor at the same time.
The association between metabolite and aggression is accommodated by means of a fixed effect, i.e., regression of metabolite on binary (0/1) or continuous aggression score.

Simulation 1. Random effects model. 

The metabolite explains 5% (r2=.05) of the variance in aggression. The heritability of metabolite is .6 (h2m=.5), the heritability of the residual of aggression is .5 (h2ag=.5). The number of batches is 70, the number of twin pairs is 600 (NMZtot=600). The true phenotypic variances of metabolite and aggression are both set to equal 1 and the variance is .25 (platevar=.25). All variables have zero mean. So the metabolite variance is 1.25. The selection is based on a mean split (high aggr>0; low aggr<0). The number of replications is 50.  All 600 pairs are in the analysis. Estimation method is by restricted ML (REML).
Conclusion: 
Allocation regime (pairs vs. individuals) has no effect on the estimate of the parameter of interest. We note that, as expected, regression on continuous predictors confers more power than regression on binary predictor (0/1). The variance components (Additive genetic, Environment and Batch) appear to be slightly downwards biased in the allocation by pair, but accurate in the allocation by individual condition. 

Simulation 2. Fixed batch effects in two steps or one step.

It may be expedient to carry out analyses in two steps, i.e., first correct for batch effects, and second carry out the analysis of actual interest. We compared one and two step analyses in simulation 2.  We used linear mixed modeling in simulation 1 (estimating the twin covariance conditional on predictor and batch). Here we use GEE (generalized estimating equations), i.e., we correct the standard errors after the analyses using a sandwich correction. That is:
One step: using GEE regress metabolite on predictor and batch simultaneously. 
Two step: first correct metabolite for batch effect and then use GEE to analyze the residuals.
Conclusions:
Conclusions are the same as those based on Simulation 1. Allocation regime (pairs vs. individuals) has little effect on the test of the parameter of interest. Again, as expected, regression of continuous predictors confers more power that regression on binary predictor (0/1). We see little differences between one and two step procedure. 

Simulation 3: More extreme selection and fixed plate effects in two step or one step.

This simulation is the same as simulation 2. However here we employ a more extreme selection criterion rather than a mean split (Simulations 1 and 2), the selection of high and low scoring twins is on the basis of the criteria > .5 std unit or < -.5 std units. As in simulation 2, we carry out one and two step analyses using GEE. Given the selection, we set the total sample size to 5000 (random sample) and select from this sample based on the criteria mentioned. 
Conclusions:
The conclusions are consistent with those of simulations 1 and 2.  The allocation regime, i.e., pairs vs. individuals, has little effect on the test of the parameter of interest. The regression of continuous predictors confers more power that regression on binary predictor (0/1), as expected.. There is little difference between the results of the one and two step procedure.


How to allocate twins to batches in assay of metabolites in the classical twin design   

Simulation 4: estimating genetic and non-genetic variance components in the twin design.

In simulation 1, we noted that batch allocation by twin pair appeared to result in a slight bias in the estimates of the variance components. In simulation 4, we examined the effect on variance components by fitting an ACE model to twin data. Here we treat batch as a random and as a fixed effect, and we carry out both one step and two step analyses. We consider relatively small sample sizes. We use linear mixed modeling with REML (restricted maximum likelihood) estimation. 
Conclusion:
The results demonstrate that allocation regime has little effect in the one step analyses, regardless of whether this is based on random effects or fixed effects modeling of batch. In the two step procedures, we note a downward bias in the estimates of the A (additive genetic) and C (common environment) variance components. This bias is greater in given the allocation by twin pairs, and greater as the number of batches increases (compare 15, 25, and 40 batch conditions). 

For details of the simulations and Settings in the R code see:

https://www.cambridge.org/core/journals/twin-research-and-human-genetics/article/establishing-a-twin-register-an-invaluable-resource-for-behavior-genetic-epidemiological-biomarker-and-omics-studies/A027C91A8B3EEBE4DE6AA5ADE49B2DA7#supplementary-materials

Reference

Odintsova VV, Willemsen G, Dolan CV, Hottenga JJ, Martin NG, Slagboom PE, Ordoñana JR, Boomsma DI. Establishing a Twin Register: An Invaluable Resource for (Behavior) Genetic, Epidemiological, Biomarker, and 'Omics' Studies. Twin Res Hum Genet. 2018 Jun;21(3):239-252. doi: 10.1017/thg.2018.23. Epub 2018 May 10. PMID: 29743129.
