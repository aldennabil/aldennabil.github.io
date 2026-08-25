---
layout: page
title: "Seasonal Commodity Price Forecasting: ETS vs. LSTM"
description: "Comparative time-series forecasting over 12 years of commodity market data, achieving 3.26% MAPE with an Optuna-optimized ETS model for food security early warnings."
importance: 4
category: timeseries
tags: [Python, PyTorch, LSTM, ETS, Optuna, Time Series Forecasting]
github: https://github.com/aldennabil/commodity-price-forecasting-ets-lstm
status: complete
year: 2025
---

## Executive Summary

Rice price volatility in West Java—a major national rice producer—critically impacts Indonesia's food security and regional inflation indices. This study evaluated classical statistical time-series forecasting against deep recurrent neural networks on **12 years of historical monthly market price data**.

The research determined optimal model architectures through **Optuna Bayesian hyperparameter optimization**, producing an early warning forecast system capable of projecting commodity fluctuations **6 months in advance**.

---

## Methodology & Model Architectures

### 1. Classical Statistical: ETS (Error, Trend, Seasonal) State-Space
- Applied additive and multiplicative Holt-Winters and ETS state-space formulations to capture pronounced seasonal harvesting cycles and long-term price trends.
- Automated parameter selection (smoothing coefficients $\alpha, \beta, \gamma$) via maximum likelihood estimation and Optuna tuning.

### 2. Deep Learning: Long Short-Term Memory (LSTM)
- Constructed multi-layer LSTM networks with sliding window lookbacks to model non-linear temporal dynamics.
- Implemented Dropout regularization and early stopping to mitigate overfitting given the limited monthly sample size regime.

---

## Key Results

| Model Architecture | MAE (IDR/kg) | RMSE (IDR/kg) | MAPE (%) |
|---|---|---|---|
| **Optimized ETS (Additive Trend, Multiplicative Seasonal)** | **312.4** | **398.2** | **3.26%** |
| LSTM Deep Neural Network | 485.6 | 612.0 | 5.14% |
| Classical SARIMA Baseline | 430.1 | 540.8 | 4.48% |

**Key Finding**: In sample-constrained macroeconomic time series, disciplined statistical state-space formulations (ETS) consistently outperform complex deep recurrent architectures by maintaining robustness against noise while remaining computationally lightweight.
