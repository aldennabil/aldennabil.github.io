---
layout: page
title: "Football Match Outcome Prediction"
description: "End-to-end ML pipeline with Elo rating reconstruction and hybrid LightGBM models across 121,000+ matches — 3rd Winner & Most Applicable, Gammafest 2026."
img: assets/img/projects/football-outcome-prediction-gammafest.png
importance: 2
category: ml
tags: [Python, LightGBM, Optuna, Feature Engineering, Elo Rating, Time Series]
github: https://github.com/aldennabil/football-outcome-prediction-gammafest
status: complete
year: 2026
competition:
  name: "Gammafest Data Science Competition 2026"
  result: "3rd Winner & Most Applicable"
featured: true
---

## Competition Overview

In the **Gammafest Data Science Competition 2026**, teams were challenged to engineer an end-to-end predictive machine learning pipeline to forecast international football scores and 3-class match outcomes across **121,000+ matches spanning 154 years of historical data (1872–2026)**.

The solution achieved **3rd Place and the "Most Applicable" Award** among nationwide university competitors.

---

## Technical Challenges & Key Innovations

### 1. Severe Feature Disparity Resolution (47 Train vs. 20 Test Features)
- A critical hurdle in the competition was a severe covariate mismatch: 47 variables were available in the training set, but only 20 metadata columns were provided in the evaluation set.
- Developed an **adaptive chronological Elo rating reconstruction** and historical state-propagation mechanism across 154 years of international fixtures.
- Generated **56 rich predictive metrics** (dynamic team strength differentials, home-field advantage scaling, rolling goal momentum, clean sheet probability) with **zero future data leakage**.

### 2. Hybrid Multi-Objective Modeling Architecture
- Implemented a parallel ensemble architecture composed of:
  - **Two Poisson Regression LightGBM Models**: Estimating expected goals for Home and Away sides independently.
  - **One Multi-Class LightGBM Classifier**: Directly optimizing the probabilities of Home Win, Draw, and Away Win.
- Coupled model outputs using **Optuna Bayesian Optimization** to minimize the competition's non-linear Asymmetric Weighted Mean Absolute Error (AW-MAE) evaluation loss.

---

## Results & Impact

| Metric / Stage | Baseline | Final Hybrid Pipeline | Improvement |
|---|---|---|---|
| **AW-MAE Loss** | 2.69 | **1.98** | **-26.4% Error Reduction** |
| **Draw F1-Score** | 0.28 | **0.43** | **+15.0% Class Sensitivity** |
| **Validation Scheme** | Random K-Fold (Overfitted) | **Chronological Out-of-Time CV** | **Robust Generalization** |

**Key Takeaway**: Preventing temporal data leakage through sequential state reconstruction was the single most decisive factor in building a model that generalized reliably to unseen future tournaments.
