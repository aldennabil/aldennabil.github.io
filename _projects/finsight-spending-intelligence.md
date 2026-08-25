---
layout: page
title: "FinSight — AI-Powered Spending Intelligence for Digital Banking"
description: "Zero-click banking transaction classification, 10-feature financial persona clustering, and Autoencoder anomaly detection with automated AI coach behavioral reports."
img: assets/img/projects/finsight-spending-intelligence.png
importance: 1
category: risk
tags: [Python, FastAPI, DistilBERT, K-Means, Autoencoders, NestJS, React Native, Streamlit]
github: https://github.com/aldennabil/finsight-spending-intelligence
status: complete
year: 2026
role: "Machine Learning Engineer & Data Scientist"
team: "CC26-PSU412 Capstone Team"
featured: true
---

## Executive Summary

**FinSight** is an end-to-end AI-powered financial intelligence system designed for modern digital banking applications. It transforms raw, unstructured transaction streams into actionable behavioral insights without requiring manual bookkeeping ("Zero-Click Tracking").

The platform integrates three core machine learning engines with a microservice architecture (React Native mobile app, NestJS backend API, FastAPI ML inference services, and Streamlit operational monitoring).

---

## Key AI Capabilities & Architecture

### 1. Zero-Click Transaction Categorization (NLP)
- Utilizes fine-tuned **DistilBERT** sequence classification to categorize merchant descriptions and unstructured transaction memos automatically.
- Eliminates manual expense logging friction while achieving high classification confidence across major spending taxonomies (Food & Beverage, Groceries, Utilities, Transportation, Entertainment, Subscriptions).

### 2. Financial Persona Profiling (Unsupervised Behavioral Segmentation)
- Extracts a **10-dimensional behavioral feature vector** updated on a rolling monthly basis:
  - Wants-to-Needs Expenditure Ratio
  - Night-Owl Spending Frequency (transactions between 22:00–04:00)
  - Weekend Surge Ratio (Saturday/Sunday discretionary spend vs. weekday baseline)
  - Savings Rate & Cash Flow Buffer
  - Impulse Index & High-Volatility Spend Variance
- Applies **K-Means Clustering** to segment users into distinct financial personas:
  - 🟢 **Balanced**: Sustainable savings rate with disciplined discretionary expenditure.
  - 🟡 **Tightwad**: Extreme loss-aversion with high savings and low lifestyle allocation.
  - 🔴 **Spendthrift**: High wants-to-needs ratio with frequent late-night or weekend spending surges.

### 3. Spending Anomaly Detection (Deep Autoencoders)
- Implements a deep **Autoencoder neural network** trained on normalized historical category-level expenditure distributions.
- Calculates reconstruction error for incoming transactions against user-specific historical thresholds, flagging statistical outliers and abnormal spikes before they disrupt budget targets.

### 4. Scheduled AI Financial Coach & Narrative Reports
- Automated reporting engine running weekly and monthly batch jobs to synthesize persona changes, savings trajectories, and flagged anomalies into actionable behavioral advice.

---

## Technical Stack

| Layer | Technologies |
|---|---|
| **ML Models & Inference** | Python, PyTorch, Scikit-Learn, DistilBERT, Autoencoders, K-Means |
| **Microservices & API** | FastAPI (ML Serving), NestJS (Core Backend API & JWT Authentication) |
| **Frontend & Mobile** | React Native (Mobile Client), Streamlit (Monitoring & Analytics Dashboard) |
| **Database & Cache** | PostgreSQL, Prisma ORM |

---

## Impact & Takeaways

FinSight demonstrates the practical translation of advanced machine learning techniques (NLP, unsupervised clustering, and semi-supervised anomaly detection) into a customer-centric digital banking solution that enhances financial awareness and decision-making.
