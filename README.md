# Hybrid Decomposition-Based Forecasting for River Nitrate Prediction

This repository contains an experiment notebook (`exp.ipynb`) that proposes a **decomposition-based hybrid forecasting framework** for **river nitrate (NO₃) time-series prediction**.

The core idea is to **decompose** the original nitrate time series into interpretable components (trend / seasonality / residual), train **multiple candidate forecasting models** per component, and then **recombine** the best component-level forecasts into a final prediction.

It also includes a comparison of **hyperparameter optimization strategies**—**Grid Search**, **Random Search**, and **WOA (Whale Optimization Algorithm)**—to evaluate how tuning approaches affect performance within this framework.

---

## Recruiter Summary (What this project demonstrates)
- Applied **time-series forecasting** for an environmental / water-quality use case (river nitrate)
- Hybrid modeling workflow combining:
  - **STL decomposition** (trend + seasonal + residual)
  - **model selection per component** based on validation performance
  - **recomposition** of component forecasts into a final series
- Experimental evaluation of **hyperparameter optimization** methods:
  - Grid Search
  - Random Search
  - Whale Optimization Algorithm (WOA)
- Reproducible research workflow in **Jupyter Notebook** (end-to-end data prep → training → evaluation → plots)

---

## How the Framework Works
### 1) STL decomposition
The original nitrate series is decomposed with **STL (Seasonal-Trend decomposition using LOESS)** into:
- **Trend component**
- **Seasonal component**
- **Residual (remainder) component**

### 2) Component-wise forecasting with model competition
For **each component**, the notebook:
1. Trains **multiple forecasting models** (candidate models)
2. Evaluates each candidate on a validation split
3. Selects the **best-performing model** for that component

### 3) Recombination
The component forecasts are **summed** to reconstruct the final forecast:

> **Final forecast = trend_forecast + seasonal_forecast + residual_forecast**

### 4) Hyperparameter optimization comparison
To understand the effect of tuning on performance, the notebook compares:
- **Grid Search** (exhaustive parameter search)
- **Random Search** (stochastic sampling)
- **WOA** (metaheuristic global optimization)

---

## Repository Contents
- `exp.ipynb` — main experiment notebook

---

## Getting Started
### Option A — Run in Google Colab (quickest)
1. Open the notebook directly in GitHub.
2. Click **“Open in Colab”** (or copy the notebook URL into Colab).

### Option B — Run locally
#### 1) Create an environment
Use either **conda** or **venv**.

```bash
python -m venv .venv
source .venv/bin/activate  # macOS/Linux
# .venv\Scripts\activate  # Windows

pip install -U pip
pip install jupyter numpy pandas scipy statsmodels scikit-learn matplotlib seaborn
