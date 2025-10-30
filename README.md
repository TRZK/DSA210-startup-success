# Early-Stage Startup Success Prediction

## Overview
Predict whether a startup survives (operating/IPO/acquired) using information from its first 18–24 months. 

## Motivation
Use early, realistic signals to compare startups without waiting for long-term outcomes.

## Data (public, enriched as required)
- Startup Success Prediction (Kaggle): https://www.kaggle.com/datasets/manishkc06/startup-success-prediction
- Startup Investments — Crunchbase (Kaggle): https://www.kaggle.com/datasets/arindam235/startup-investments-crunchbase/

## Plan for Data Collection & Preparation
- Download both datasets from Kaggle.
- Basic cleaning (drop junk cols, parse dates, standardize names/locations).
- Simple enrichment: align companies across the two files (prefer exact keys like permalink).
- Limit features to information available in the first ~24 months after founding.
