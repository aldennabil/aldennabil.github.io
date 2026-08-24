---
layout: page
title: "Football Match Outcome Prediction"
description: "Ensemble machine learning for three-class match result prediction (H/D/A) — 3rd place, GammaFest 2025 Data Science Competition."
img: assets/img/projects/football-outcome-prediction-gammafest.png
importance: 2
category: ml
tags: [Python, XGBoost, LightGBM, Scikit-learn, Ensemble]
github: https://github.com/aldennabil/football-outcome-prediction-gammafest
status: complete
year: 2025
competition:
  name: "GammaFest 2025 Data Science Competition"
  result: "3rd Place"
---

## Problem

Football match outcome prediction is a three-class classification problem — Home Win, Draw, or Away Win — with high inherent variance and systematic class imbalance (draws are underrepresented). The task required a model that generalizes across leagues and seasons without data leakage from future match information.

## Approach

{% include figure.liquid
   path="assets/img/projects/football-outcome-prediction-gammafest.png"
   class="img-fluid rounded"
   caption="Feature importance from the stacked ensemble. ELO rating differential and rolling goal difference were the strongest predictors; raw match metadata alone produced near-baseline results." %}

Feature engineering was the critical differentiator:

- **ELO ratings** — Team strength scores updated incrementally after each match, using the standard ELO update formula with a K-factor calibrated to the dataset
- **Rolling statistics** — Win rate, goal difference, and clean sheet rate computed over 5, 10, and 20-match windows to capture current form
- **Temporal cross-validation** — Splits by season, not randomly, to prevent future data from leaking into training

Base learners (XGBoost, LightGBM, Logistic Regression) were trained independently, then their out-of-fold predictions served as features for a Ridge meta-learner — the stacking layer. An ablation study confirmed which feature groups drove performance.

## Results

| Model | Weighted F1 |
|-------|-------------|
| Logistic Regression (baseline) | — |
| XGBoost | — |
| LightGBM | — |
| **Stacked Ensemble** | **Best** |

**Competition outcome: 3rd Place — GammaFest 2025**

Draw prediction improved by ~8 percentage points after Platt scaling threshold calibration, the hardest class across all runs.

## Reflection

Temporal leakage was the main trap: random k-fold inflated validation scores by a significant margin compared to season-based splits. The lesson transfers directly to financial time series — always validate on out-of-time data.

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  <a href="https://github.com/aldennabil/football-outcome-prediction-gammafest" class="btn btn-sm z-depth-0" role="button" target="_blank">
    View on GitHub
  </a>
</div>
