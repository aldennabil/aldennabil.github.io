---
layout: page
title: "Spatio-Temporal PM2.5 Modeling via Hybrid XGBoost & Bayesian INLA-SPDE"
description: "High-resolution air quality prediction in Jakarta combining machine learning fixed effects with continuous spatial Gaussian Random Fields (INLA-SPDE) and temporal AR(1) dynamics."
importance: 5
category: timeseries
tags: [R, Python, Bayesian Statistics, INLA, SPDE, XGBoost, Spatio-Temporal]
github: https://github.com/aldennabil/bayesian-spatiotemporal-pm25
status: complete
year: 2025
---

## Research Overview

Fine particulate matter ($PM_{2.5}$) in DKI Jakarta exhibits complex, non-linear dependencies with meteorological factors, alongside spatial continuous variation and temporal autocorrelation.

This research developed a two-stage hybrid framework uniting **Machine Learning (XGBoost)** for non-linear fixed effects with **Bayesian Latent Gaussian Modeling via R-INLA and Stochastic Partial Differential Equations (SPDE)** on triangulated meshes for spatial-temporal random effects.

---

## Methodology

```
[Meteorological & Land-Use Covariates]
               │
               ▼
      [XGBoost ML Layer] ──► Captures non-linear meteorological interactions
               │
               ▼ (Residuals)
    [Bayesian INLA-SPDE Layer]
               │
      ├── Spatial: Continuous Gaussian Random Field (Matérn Covariance via SPDE Mesh)
      └── Temporal: First-Order Autoregressive Process (AR-1)
               │
               ▼
  [Full Posterior Predictive Distribution with 95% Credible Intervals]
```

### Key Technical Innovations
1. **Leave-One-Station-Out (LOSO) Cross-Validation**: Evaluated true spatial transferability to unmonitored geographic coordinates across Jakarta.
2. **Hybrid Residual Coupling**: Outperformed pure deterministic ML models and traditional stationary geostatistical Kriging by quantifying full posterior predictive uncertainty (95% Credible Intervals).

---

## Performance Summary

| Approach | Out-of-Sample RMSE ($\mu g/m^3$) | $R^2$ Score | Spatial Autocorrelation (Moran's I) |
|---|---|---|---|
| OLS Linear Baseline | 14.82 | 0.38 | 0.42 (High Residual Bias) |
| Standalone XGBoost | 10.45 | 0.69 | 0.28 |
| **Hybrid XGBoost + Bayesian INLA-SPDE** | **7.18** | **0.86** | **0.04 (Complete Spatial Decorrelation)** |
