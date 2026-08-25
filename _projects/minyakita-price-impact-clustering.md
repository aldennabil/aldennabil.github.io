---
layout: page
title: "Minyakita Price Impact Analysis via Spatial Clustering"
description: "K-Means and hierarchical clustering on 38 Indonesian provinces to evaluate the market stabilization effect of government-subsidized Minyakita on packaged cooking oil prices."
importance: 17
category: analytics
tags: [Python, K-Means Clustering, Geospatial Analysis, Folium, Economics]
github: https://github.com/aldennabil/minyakita-price-impact-clustering
status: complete
year: 2024
---

## Overview

In response to nationwide cooking oil price inflation, the Indonesian government launched the subsidized "Minyakita" initiative to stabilize consumer market prices.

This project evaluated price transmission dynamics and regional market responsiveness across **38 Indonesian provinces and 514 regencies/cities**, identifying spatial disparity clusters using unsupervised machine learning.

---

## Analytical Methodology

1. **Feature Engineering on Price Time Series**:
   - Derived pre- and post-launch price change deltas ($\Delta \text{Price}$), coefficient of variation ($CV$), and supply disparity indices from daily PIHPS market price feeds.
2. **Unsupervised Clustering (K-Means & Hierarchical)**:
   - Determined optimal $k=3$ clusters via Silhouette Score (0.64) and Elbow Method:
     - **Cluster 1 (Fast Stabilizers)**: Western Indonesia / Java-Bali regions with rapid price reversion to ceiling targets ($HET$).
     - **Cluster 2 (Moderate Lag)**: Sumatra and Kalimantan regions with 4–6 week delayed market stabilization.
     - **Cluster 3 (High-Friction Outliers)**: Eastern Indonesia (Papua, Maluku) maintaining elevated price volatility due to logistical bottlenecks.
3. **Interactive Geospatial Visualization**:
   - Rendered interactive Folium choropleth maps linking cluster assignments with GADM 4.1 boundary geo-data.
