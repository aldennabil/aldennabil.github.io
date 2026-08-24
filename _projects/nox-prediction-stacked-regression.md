---
layout: page
title: "NOx Prediction via Stacked Regression"
description: "Ensemble stacking of multiple regression learners to predict nitrogen oxide emissions, outperforming all individual base models — DBS Datamatika 2026."
img: assets/img/projects/nox-prediction-stacked-regression.png
importance: 3
category: ml
tags: [Python, Scikit-learn, XGBoost, LightGBM, Ensemble]
github: https://github.com/aldennabil/nox-prediction-stacked-regression
status: complete
year: 2026
competition:
  name: "DBS Datamatika 2026"
---

## Problem

Predicting NOx emissions from combustion process variables is a regression task where no single model family dominates. Stacked generalization — training a meta-learner on the out-of-fold predictions of base models — is theoretically motivated by the complementarity of learner error patterns.

## Approach

{% include figure.liquid
   path="assets/img/projects/nox-prediction-stacked-regression.png"
   class="img-fluid rounded"
   caption="Actual vs. predicted NOx values for the stacked ensemble on the held-out test set. The stacked model reduces systematic over- and under-prediction visible in the individual base learners." %}

**Stacking pipeline:**

1. Training data split into 5 folds
2. Each base learner (Ridge, Random Forest, XGBoost, LightGBM, SVR) trained on 4 folds, predicts on the held-out fold — producing out-of-fold (OOF) predictions that are not contaminated by training data
3. OOF predictions from all base learners form the meta-feature matrix
4. A Ridge meta-learner trained on this matrix produces the final prediction
5. Test predictions: average of base learners' full-training predictions, fed into the meta-learner

This approach prevents data leakage at the stacking layer, unlike naive blending.

## Results

| Model | RMSE | Improvement over baseline |
|-------|------|---------------------------|
| Ridge (baseline) | — | — |
| Random Forest | — | — |
| XGBoost | — | — |
| **Stacked Ensemble** | **Lowest** | **Best** |

The stacked ensemble consistently outperformed all individual learners, confirming that error patterns were sufficiently uncorrelated across model families to benefit from aggregation.

## Reflection

The key implementation detail is using out-of-fold predictions — not in-sample predictions — to train the meta-learner. Getting this wrong is a common source of overly optimistic stacking performance.

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  <a href="https://github.com/aldennabil/nox-prediction-stacked-regression" class="btn btn-sm z-depth-0" role="button" target="_blank">
    View on GitHub
  </a>
</div>
