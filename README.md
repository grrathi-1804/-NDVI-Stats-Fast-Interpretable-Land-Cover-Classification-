# NDVI-Stats: Fast & Interpretable Land Cover Classification

**Short description (for resume):**
Classify land cover types using NDVI time-series data from satellite imagery and OpenStreetMap (OSM) labels. Built a Logistic Regression model robust to noisy NDVI signals.

## Problem
This project addresses the Hackathon problem *"NDVI-based Land Cover Classification"*. The goal is to predict land cover classes (Water, Impervious, Farm, Forest, Grass, Orchard) from 27 NDVI time points per sample, despite noise from cloud cover and imperfect OSM labels.

## Dataset
- Each row includes: `ID`, `class` and 27 NDVI time-point columns (e.g., `20150720_N`).
- Challenges: noise, missing values, temporal/seasonal variation.

## Approach
- Preprocessing: denoising & imputation for missing NDVI (due to cloud cover).
- Feature engineering: summary statistics from NDVI time series (mean, std, skew, kurtosis), trend features, seasonal aggregates.
- Model: Multiclass Logistic Regression (requirement of the hackathon).
- Evaluation: accuracy on public/private leaderboard split (public = 89%, private = 11%).

## Repository structure
```
NDVI_Project/
├── notebooks/
│   └── NDVI_Stats_Land_Cover_Classification.ipynb
├── src/
│   └── (optional scripts for preprocessing / modeling)
├── data/               # don't upload large raw datasets; include small samples if needed
├── requirements.txt
├── README.md
├── .gitignore
```

## Results (from notebook)
- Validation accuracy: **~86.6%** (Logistic Regression with NDVI statistical features).
- Model is simple, interpretable, and focuses on generalization under noisy training conditions.

## How to run
1. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # on Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```
2. Open the notebook:
   ```bash
   jupyter lab notebooks/NDVI_Stats_Land_Cover_Classification.ipynb
   ```
3. Reproduce: run cells in order. If required, place a small sample dataset in `data/` with the same columns.

## Future Work
- Try robust imputation methods or temporal models (e.g., simple RNNs) while keeping explainability.
- Add cross-validation and confusion matrix visualizations for per-class insights.

## Contact
Gaurav Rathi — GitHub: [grrathi-1804](https://github.com/grrathi-1804) — Email: grrathi1804@gmail.com
