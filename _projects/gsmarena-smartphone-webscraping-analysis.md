---
layout: page
title: "Smartphone Market Web Scraping & Pricing Regression"
description: "Automated web scraping pipeline in R (rvest) extracting smartphone hardware specifications from GSMArena coupled with statistical pricing elasticity modeling."
importance: 18
category: analytics
tags: [R, rvest, Web Scraping, Feature Transformation, Linear Regression]
github: https://github.com/aldennabil/gsmarena-smartphone-webscraping-analysis
status: complete
year: 2024
---

## Overview

Pricing strategies in the consumer electronics sector depend heavily on hardware specifications and brand positioning.

This project built an automated data extraction and statistical analysis pipeline in **R (`rvest`)** to scrape, clean, and model smartphone pricing drivers across hundreds of smartphone models listed on GSMArena.

---

## Technical Pipeline

1. **Web Scraping & Ingestion**:
   - Automated HTML parsing routines extracting semi-structured table fields (RAM, internal storage, battery capacity, camera sensor count, display resolution, chipset, 5G band support).
2. **Text Parsing & Feature Transformation**:
   - Cleaned messy string metrics (e.g. converting `"5000 mAh"`, `"8GB RAM"`, `"108 MP, f/1.8"`) into standardized numeric variables.
3. **Statistical Regression Modeling**:
   - Log-linear regression modeling to isolate hardware pricing premiums:
     $$\ln(\text{Price}) = \beta_0 + \beta_1 \ln(\text{RAM}) + \beta_2 \ln(\text{Storage}) + \beta_3 (\text{Battery}) + \sum \gamma_k \text{Brand}_k + \varepsilon$$

---

## Key Findings

- Storage capacity and brand tier accounted for over 64% of price variance ($R^2 = 0.782$), while 5G connectivity carried an average 18.5% price premium controlling for other core hardware specifications.
