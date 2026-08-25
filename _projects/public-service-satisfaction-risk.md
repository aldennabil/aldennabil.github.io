---
layout: page
title: "Public Service Dissatisfaction Risk Modeling"
description: "Statistical risk scoring, logistic classification, and priority segmentation matrices to identify drivers of citizen dissatisfaction across municipal public services."
importance: 11
category: risk
tags: [Python, Logistic Regression, Survey Analytics, Risk Segmentation]
github: https://github.com/aldennabil/public-service-satisfaction-risk
status: complete
year: 2024
---

## Overview

Municipal governments require data-driven mechanisms to prioritize budget allocations and operational improvements across diverse public service sectors.

This project developed a comprehensive risk analysis and citizen segmentation framework to model the probability of citizen dissatisfaction across municipal public services (Infrastructure & Environment, Social Services & Education, Administration & Licensing, and Public Healthcare).

---

## Analytical Methodology

1. **Service Sector Priority Matrix**:
   - Mapped complaint volumes against dissatisfaction rates to isolate **High Priority Quadrants** (High Volume, High Dissatisfaction).
2. **Multivariable Risk Scoring Model**:
   - Built a regularized Logistic Regression risk model to estimate the odds of citizen dissatisfaction based on processing time delays, staff responsiveness, and transparency indices.
3. **Interpretability & Policy Insights**:
   - Identified administrative processing delays in Licensing and Infrastructure as the primary contributors to public dissatisfaction risk (Odds Ratio = 2.34, $p < 0.01$).
