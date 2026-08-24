---
layout: page
title: "Market Research Analytics Platform"
description: "Full-stack statistical system: ETL pipeline, SQLite normative database, and Streamlit dashboard for benchmarking product performance across survey categories."
img: assets/img/projects/market-research-analytics-platform.png
importance: 1
category: engineering
tags: [Python, SQLite, Streamlit, Pandas, ETL]
github: https://github.com/aldennabil/market-research-analytics-platform
status: complete
year: 2025
---

## Problem

Market research firms accumulate historical survey data across product categories and client studies. Without a centralized system, benchmarking a new product against historical norms requires manual, error-prone Excel work. This project replaces that process with a production-grade normative database and self-service dashboard.

## Architecture

{% include figure.liquid
   path="assets/img/projects/market-research-analytics-platform.png"
   class="img-fluid rounded"
   caption="System architecture: survey workbooks ingested through a validated ETL pipeline into a SQLite database, queried in real time by a Streamlit dashboard." %}

The system is organized into four layers:

1. **Validation** — Schema checks, Likert naming format verification, straight-line respondent flagging, and casing standardization before any write operation
2. **ETL Pipeline** — Parses Excel workbooks, separates 5-point and 7-point Likert scales, and loads structured records into SQLite using WAL journal mode for fast concurrent writes
3. **Norm Cache** — Pre-computed percentile cutoffs, Top Box (T2B/T3B), and mean scores stored at ingestion time for sub-second dashboard queries
4. **Streamlit Dashboard** — Four pages: database overview, norm explorer with category filters, product comparator for benchmarking new entries, and a data ingestion portal with automated backup

## Technical Highlights

- Schema-enforced ingestion with 12 structural validation rules — invalid uploads are rejected with a detailed error log
- Automated timestamped backups of both the SQLite database and ingested Excel files before every write
- SQLite configured to WAL + NORMAL synchronous mode; norm queries return in under one second on the full dataset
- Clean separation between research code (`research/`) and production source (`src/`, `app/`) — the dashboard has no dependency on development notebooks

## Limitations

Survey data is proprietary and not included in this repository. The system is designed for a specific Excel schema; adapting to other survey formats requires modifications to the validation and ETL layers.

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  <a href="https://github.com/aldennabil/market-research-analytics-platform" class="btn btn-sm z-depth-0" role="button" target="_blank">
    View on GitHub
  </a>
</div>
