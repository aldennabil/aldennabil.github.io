---
layout: page
title: "Credit Risk Survival Analysis"
description: "Non-parametric Kaplan-Meier time-to-event modeling and life-table estimation for customer default and banking churn risk."
importance: 8
category: risk
tags: [R, Survival Analysis, Kaplan-Meier, Credit Risk, Banking]
github: https://github.com/aldennabil/credit-risk-survival-analysis
status: complete
year: 2024
---

## Overview

Traditional binary credit scoring models (e.g. Logistic Regression) predict *whether* a borrower defaults within a fixed observation window, but cannot answer *when* default is most likely to occur or handle right-censored loan contracts.

This project applied time-to-event survival analysis to banking credit portfolios, modeling temporal default probabilities and survival curves across customer demographic and credit profile tiers.

---

## Analytical Methodology

1. **Non-Parametric Survival Estimation**:
   - Constructed **Kaplan-Meier survival curves** $S(t)$ to estimate cumulative non-default probabilities over loan tenures.
   - Performed **Log-Rank tests** and Wilcoxon tests to identify statistically significant divergence in default timing across credit score bands and collateral types.
2. **Actuarial Life-Table Construction**:
   - Derived discrete monthly hazard rates $h(t)$, conditional failure probabilities, and cumulative survival rates for portfolio provisioning and liquidity planning.

---

## Key Insights

- High-risk sub-prime loan tranches exhibited peak hazard concentration between months 6 and 14, indicating that early intervention monitoring produces the highest risk reduction dividend.
- Verified proportional hazard assumptions across stratified collateral tiers.
