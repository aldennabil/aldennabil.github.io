---
layout: page
title: "Regional Economic Growth Modeling via Box-Cox & Stepwise Regression"
description: "Econometric modeling of regional economic growth across Java Island using BPS SUSENAS 2023 microdata with Box-Cox power transformations and stepwise feature selection."
importance: 14
category: stats
tags: [R, Box-Cox Transformation, Stepwise Regression, Econometrics, BPS SUSENAS]
github: https://github.com/aldennabil/susenas-boxcox-stepwise-regression
status: complete
year: 2024
---

## Problem & Background

Regional economic disparities across Java Island are reflected in per capita household expenditure patterns documented in the National Socioeconomic Survey (SUSENAS 2023) by Statistics Indonesia (BPS).

Raw expenditure microdata exhibits severe positive skewness, heavy tails, and heteroskedastic error structures that violate classical linear model assumptions.

---

## Statistical Methodology

1. **Box-Cox Power Transformation**:
   - Estimated optimal transformation parameter $\hat{\lambda} = 0.23$ via Profile Log-Likelihood maximization:
     $$y^{(\lambda)} = \begin{cases} \frac{y^\lambda - 1}{\lambda}, & \lambda \neq 0 \\ \ln(y), & \lambda = 0 \end{cases}$$
   - Restored normality in model residuals (Kolmogorov-Smirnov test $p > 0.05$) and stabilized variance across income percentiles.
2. **Stepwise Variable Selection (AIC & BIC)**:
   - Automated bi-directional feature elimination across education levels, labor sector participation, household size, and access to digital infrastructure.

---

## Key Results

- **Model Diagnostics**: Adjusted $R^2$ increased from 0.48 (untransformed model with non-normal residuals) to **0.72** under the Box-Cox transformed specification.
- **Top Determinants**: Tertiary education attainment rate and digital technology adoption demonstrated the highest positive elasticity with regional per capita expenditure growth.
