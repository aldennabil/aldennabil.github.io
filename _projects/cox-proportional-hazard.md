---
layout: page
title: "Cox Proportional Hazards for Clinical Survival"
description: "Semi-parametric survival modeling, Schoenfeld residual diagnostics, and hazard ratio estimation on cardiovascular clinical event data."
importance: 10
category: risk
tags: [R, Survival Analysis, Cox PH, Hazard Ratios, Healthcare Analytics]
github: https://github.com/aldennabil/cox-proportional-hazard
status: complete
year: 2024
---

## Overview

Cox Proportional Hazards regression is the standard semi-parametric technique for estimating covariate effects on the hazard rate without assuming a specific baseline hazard distribution.

This project applied Cox PH regression to heart failure clinical trial datasets, diagnosing proportional hazards assumptions and quantifying relative mortality risks.

---

## Statistical Diagnostics

1. **Proportional Hazards Assumption Testing**:
   - Evaluated **Schoenfeld residuals** over time to ensure time-invariance of covariate effects ($\beta(t) = \beta$).
   - Plotted $-\ln(-\ln(S(t)))$ log-log survival curves across clinical strata.
2. **Hazard Ratio Estimation**:
   - Derived Adjusted Hazard Ratios (HR) with 95% Confidence Intervals for clinical risk biomarkers (ejection fraction, serum creatinine, hypertension status).

---

## Key Findings

- Ejection Fraction and Serum Creatinine were identified as the strongest independent risk multipliers ($p < 0.001$), with validated proportional hazard consistency across all observation periods.
