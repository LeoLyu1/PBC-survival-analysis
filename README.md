# PBC Survival and Competing Risks Analysis

Analyzed primary biliary cirrhosis data to compare associations between clinical biomarkers and survival across baseline Cox, time-varying Cox, and Fine–Gray competing risks models in R.

## Approach

- **Data preparation:** Used the `pbc` and `pbcseq` datasets from the R survival package, retained patients with treatment assignments, and log-transformed bilirubin. Converted repeated measurements into start–stop intervals for longitudinal modeling.
- **Survival modeling:** Explored treatment-group survival with Kaplan–Meier curves and a log-rank test. Fitted univariate and multivariable Cox models using demographic and clinical predictors, and assessed proportional hazards with Schoenfeld residual tests.
- **Time-varying analysis:** Fitted an extended Cox model with updated biomarker measurements and patient-clustered robust standard errors.
- **Competing risks:** Applied a Fine–Gray model with death as the event of interest and transplantation as a competing event. Compared estimates using hazard ratios, 95% confidence intervals, and forest plots.

## Results

The poster reports that higher log-bilirubin was associated with increased mortality hazard in the baseline Cox model (**HR: 2.33; 95% CI: 1.91–2.84**), while higher albumin was associated with lower hazard (**HR: 0.43; 95% CI: 0.27–0.70**). The Fine–Gray model showed similar directions for log-bilirubin (**subdistribution HR: 2.22**) and albumin (**0.46**).

The treatment-group log-rank test was not statistically significant (**p = 0.75**). Proportional hazards tests flagged edema and prothrombin time; updating covariates does not by itself resolve nonproportional effects.

## Code and Poster

- [Analysis poster](survival_analysis_poster.pdf)
- [R Markdown source](pbc_survival_analysis.Rmd)

**Tools:** R, survival, survminer, cmprsk, dplyr, ggplot2, broom, car, and purrr.

Data are included in the survival package. The source and poster are provided as supplied; the analysis has not been rerun for this upload.
