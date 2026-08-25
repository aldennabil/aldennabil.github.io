---
layout: page
title: "NOx Emission Prediction via Stacked Regression"
description: "Two-layer stacked ensemble for gas turbine NOx emissions, optimizing sensor multicollinearity for industrial compliance — DBS Datamatika 2026."
importance: 6
category: ml
tags: [Python, Scikit-learn, XGBoost, LightGBM, CatBoost, Stacking]
github: https://github.com/aldennabil/nox-prediction-stacked-regression
status: complete
year: 2026
competition:
  name: "DBS Datamatika 2026"
---

## Problem & Motivation

Nitrogen oxides ($NO_x$) from gas turbines are major environmental pollutants subject to strict regulatory caps. Continuous Emission Monitoring Systems (CEMS) hardware is expensive and prone to sensor drift. A high-accuracy soft-sensing predictive model serves as a reliable redundant monitoring mechanism.

The core challenge lies in the complex thermodynamic interdependencies between turbine operating parameters (compressor discharge pressure, ambient temperature, air filter differential pressure, and turbine exhaust pressure).

---

## Architecture: Two-Layer Stacked Ensemble

```
Input Sensor Features (36,733 hourly observations, 11 parameters)
                          │
         ┌────────────────┼────────────────┐
         ▼                ▼                ▼
     [XGBoost]       [LightGBM]       [CatBoost]  (Layer 1: Base Learners)
         │                │                │
         └────────────────┼────────────────┘
                          ▼
            [Out-of-Fold Prediction Matrix]
                          │
                          ▼
             [Ridge / ElasticNet Meta-Learner]    (Layer 2: Stacking Layer)
                          │
                          ▼
            [Final NOx Emission Prediction]
```

### Key Engineering Decisions
- **Out-of-Fold (OOF) Prediction Matrix**: Prevented meta-learner overfitting by enforcing strict 5-fold cross-validation when generating first-layer training targets.
- **Multicollinearity Attenuation**: The diverse loss surfaces of gradient-boosted trees combined with L2-regularized meta-regression reduced variance across high-temperature turbine operating states.

---

## Results

| Model Architecture | RMSE | MAE | $R^2$ Score |
|---|---|---|---|
| Linear Regression Baseline | 8.42 | 6.18 | 0.68 |
| Standalone XGBoost | 4.81 | 3.22 | 0.89 |
| Standalone LightGBM | 4.75 | 3.19 | 0.90 |
| **Stacked Ensemble (XGB + LGB + CatBoost + Ridge)** | **4.12** | **2.81** | **0.93** |
