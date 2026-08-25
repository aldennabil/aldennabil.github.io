---
layout: page
title: "HIV Clinical Trial Survival Analysis"
description: "Time-to-event survival modeling on the ACTG 175 clinical trial comparing single vs combined antiretroviral therapies using Python's lifelines library."
importance: 16
category: stats
tags: [Python, lifelines, Kaplan-Meier, Cox PH, Log-Rank Test]
github: https://github.com/aldennabil/hiv-clinical-trial-survival
status: complete
year: 2024
---

## Overview

The AIDS Clinical Trials Group Study 175 (ACTG 175) randomized 2,139 HIV-1-infected patients to evaluate the efficacy of zidovudine (ZDV) monotherapy versus combination antiretroviral regimens (ZDV + didanosine, ZDV + zalcitabine, or didanosine alone).

This project conducted a comprehensive survival analysis using Python's `lifelines` package to evaluate disease progression and CD4 count degradation over time.

---

## Analytical Methodology

1. **Kaplan-Meier Estimation & Stratification**:
   - Estimated survival curves for time to >50% CD4 cell decline or AIDS progression.
   - Evaluated survival differences using Log-Rank and Peto-Peto tests ($p < 0.001$).
2. **Cox Proportional Hazards Modeling**:
   - Estimated Adjusted Hazard Ratios (aHR) controlling for baseline CD4 count, Karnofsky performance score, and prior antiretroviral exposure history.

---

## Clinical Takeaways

- Combination antiretroviral therapies exhibited significantly superior survival duration compared to ZDV monotherapy ($aHR = 0.58, 95\% \text{ CI } [0.47, 0.71]$), confirming the clinical value of multi-drug regimens in delaying viral progression.
