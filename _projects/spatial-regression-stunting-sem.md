---
layout: page
title: "Regional Stunting Determinants via Spatial Error Modeling (SEM)"
description: "Spatial econometric modeling comparing Ordinary Least Squares (OLS) and Spatial Error Models (SEM) to identify regional determinants of stunting prevalence in Central Java."
importance: 13
category: stats
tags: [R, Spatial Statistics, SEM, SAR, OLS, Spatial Autocorrelation]
github: https://github.com/aldennabil/spatial-regression-stunting-sem
status: complete
year: 2024
---

## Overview

Stunting prevalence among children under five exhibits strong geographic clustering due to shared regional environmental factors, healthcare infrastructure, and socioeconomic conditions.

Standard Ordinary Least Squares (OLS) regression violates the assumption of independent and identically distributed ($i.i.d.$) errors when spatial autocorrelation is present. This project evaluated **Spatial Econometric Models (SEM and SAR)** across 35 regencies and cities in Central Java (2023).

---

## Spatial Econometric Framework

1. **Spatial Weight Matrix ($W$)**: Constructed Queen Contiguity spatial connectivity matrix standardized by row totals.
2. **Spatial Diagnostics**:
   - **Global Moran's I**: Detected statistically significant spatial autocorrelation in stunting rates ($I = 0.384, p < 0.001$).
   - **Lagrange Multiplier (LM) Tests**: LM-Error ($p = 0.008$) indicated that spatial error dependence was the dominant process over spatial lag.
3. **Spatial Error Model Formulation**:
   $$y = X\beta + u, \quad u = \lambda W u + \varepsilon, \quad \varepsilon \sim \mathcal{N}(0, \sigma^2 I)$$

---

## Model Comparison

| Criterion | OLS Linear Regression | Spatial Error Model (SEM) |
|---|---|---|
| **$R^2$ Score** | 0.542 | **0.689** |
| **AIC (Akaike Info Criterion)** | 158.7 | **142.1 (Best)** |
| **Residual Moran's I** | 0.248 ($p = 0.012$, Autocorrelated) | **0.012 ($p = 0.412$, White Noise)** |

**Policy Takeaway**: Exclusive breastfeeding coverage, maternal anemia rate, and sanitation access were identified as the strongest spatial determinants, guiding targeted inter-regency interventions.
