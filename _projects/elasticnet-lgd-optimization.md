---
layout: page
title: "Superconductor Critical Temperature Optimization via Elastic Net"
description: "Resolving high multicollinearity on 21,197 samples and 81 predictors using SGD vs custom Proximal Gradient Descent (PGD/ISTA) (R² = 0.733)."
importance: 12
category: stats
tags: [Python, Optimization, ElasticNet, SGD, ISTA, Coordinate Descent]
github: https://github.com/aldennabil/elasticnet-lgd-optimization
status: complete
year: 2026
---

## Problem & Theoretical Formulation

Predicting the superconducting critical temperature ($T_c$) based on elemental chemical descriptors requires handling severe multicollinearity across **81 correlated physical predictors** across **21,197 samples** (UCI Superconductivity dataset).

The Elastic Net penalty combines $L_1$ (Lasso) sparsity with $L_2$ (Ridge) grouping:

$$\min_{\beta} \frac{1}{2n} \|y - X\beta\|_2^2 + \lambda \left( \alpha \|\beta\|_1 + \frac{1-\alpha}{2} \|\beta\|_2^2 \right)$$

---

## Optimization Algorithms Implemented

1. **Stochastic Gradient Descent (SGD)** with adaptive learning rate schedules.
2. **Custom Proximal Gradient Descent (PGD / ISTA)** utilizing the soft-thresholding operator $\text{prox}_{\lambda \alpha \|\cdot\|_1}(\cdot)$ for exact non-smooth $L_1$ regularizer handling.

---

## Comparative Results

| Optimization Method | Best Hyperparameters ($\alpha, \lambda$) | $R^2$ Score | RMSE (Kelvin) | Non-Zero Coefs |
|---|---|---|---|---|
| OLS Baseline | None | 0.672 (Unstable) | 20.45 K | 81 |
| Custom PGD (ISTA) | $\alpha=0.3, \lambda=0.01$ | 0.708 | 18.54 K | 48 |
| **Tuned SGD Elastic Net** | $\alpha=0.5, \lambda=0.005$ | **0.733** | **17.72 K** | **52** |

**Outcome**: The Elastic Net effectively eliminated redundant elemental features while maintaining stable grouped selections, providing an interpretable descriptor subset for material physics.
