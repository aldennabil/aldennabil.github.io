---
layout: page
title: "Bank Customer Churn & Membership Prediction"
description: "Supervised classification and imbalanced sampling strategies (SMOTE, Class Weighting) to predict customer churn in retail banking."
importance: 9
category: risk
tags: [R, Logistic Regression, Random Forest, Imbalanced Data, ROC-AUC]
github: https://github.com/aldennabil/bank-membership-prediction
status: complete
year: 2024
---

## Overview

Customer attrition represents substantial revenue loss for retail banks. This project developed a statistical and machine learning classification pipeline to predict customer churn and identify high-risk accounts prior to account closure.

---

## Methodology & Pipeline

1. **Handling Severe Class Imbalance**:
   - Evaluated SMOTE (Synthetic Minority Over-sampling Technique), Random Under-Sampling, and Cost-Sensitive Loss Functions to avoid majority-class prediction bias.
2. **Model Evaluation**:
   - Compared Regularized Logistic Regression, Decision Trees, and Random Forests.
   - Evaluated models using ROC-AUC, PR-AUC (Precision-Recall Area Under Curve), and Expected Cost-Weighted Misclassification Loss.

---

## Performance Summary

- **Best Model**: Random Forest with tuned decision threshold (ROC-AUC = 0.864, Sensitivity = 78.2%).
- **Top Predictors**: Number of active banking products, estimated balance volatility, credit card utilization rate, and customer activity score.
