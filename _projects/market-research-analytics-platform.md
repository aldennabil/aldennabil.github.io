---
layout: page
title: "Centralized Normative Database & Benchmarking Platform"
description: "ETL pipeline, statistical norm calculation engine, and interactive Streamlit analytics platform consolidating 17 survey projects and 8,800+ observations."
img: assets/img/projects/market-research-analytics-platform.png
importance: 3
category: analytics
tags: [Python, SQLite, Streamlit, ETL, Statistical Computing, Data Pipelines]
github: https://github.com/aldennabil/market-research-analytics-platform
status: complete
year: 2026
featured: true
---

## Overview

In commercial market research and sensory benchmarking, historical product evaluations are frequently fragmented across disparate spreadsheet formats, inconsistent scale conventions, and non-standardized column naming schemas.

This project delivered an end-to-end data platform that centralizes **17 disparate research projects (8,800+ individual consumer observations)** into a unified relational data warehouse, coupled with an automated statistical norm calculation engine and self-service analytics dashboard.

*(Client identity, proprietary brand names, and sensitive commercial survey contents are fully redacted).*

---

## Core System Architecture

### 1. Robust Ingestion & Automated Standardization ETL
- Ingestion engine with automated schema validation and column mapping rules capable of parsing varied survey exports.
- Standardizes diverse measurement formats (5-point, 7-point, and 9-point mixed Likert scales) into harmonized comparative metrics.
- Enforces strict data integrity checks, duplicate detection, and automated backup routines.

### 2. Algorithmic Statistical Norm Engine
- Computes comprehensive parametric and non-parametric historical benchmarks across product categories:
  - **Parametric Metrics**: Mean, Standard Deviation, Standard Error.
  - **Top-Box Scores**: Top-Box (TB), Top-2-Box (T2B), and Top-3-Box (T3B) acceptance proportions.
  - **Percentile Distributions**: 25th (P25), 50th (Median), and 75th (P75) percentile distributions.

### 3. Self-Service Streamlit Analytics Dashboard
- Interactive web portal enabling research analysts and executive stakeholders to query historical normative baselines dynamically.
- Allows self-service ingestion of newly completed survey datasets with instant benchmarking against historical category percentiles.

---

## Key Metrics & Impact

| Metric | Before Implementation | After Implementation |
|---|---|---|
| **Benchmarking Turnaround** | 2–3 Days (Manual Excel Lookup) | **< 5 Seconds (Automated Engine)** |
| **Data Coverage** | Dispersed in 17 separate files | **1 Unified Relational Database (8,800+ obs)** |
| **Scale Compatibility** | Manual conversion prone to errors | **Algorithmic Standardization** |
