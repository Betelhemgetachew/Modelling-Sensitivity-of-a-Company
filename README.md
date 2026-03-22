# Modelling-Sensitivity-of-a-Company

## CAPM Simulation & Regression Analysis

---

## Overview

This project simulates monthly stock prices for company XYZ over a 5-year period (2021–2025)
using Geometric Brownian Motion (GBM), constructs a CAPM regression model, and interprets
the results. It was completed as part of the Spring 2026 Practical Assessment for MTH3010A
Mathematical Finance.

---

## Files

| File | Description |
|------|-------------|
| `MTH3010A_Practical1_CAPM.ipynb` | Main Jupyter notebook containing all code, outputs, and interpretation |

---

## Requirements
```bash
pip install numpy pandas statsmodels matplotlib
```

| Library | Purpose |
|---------|---------|
| `numpy` | Random number generation, GBM simulation |
| `pandas` | DataFrame construction and manipulation |
| `statsmodels` | OLS regression (CAPM model) |
| `matplotlib` | Plotting stock price path and CAPM scatter |

---

## How to Run

1. Open `MTH3010A_Practical1_CAPM.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells in order (`Kernel → Restart & Run All`)

---

## Notebook Structure

| Cell | Task | Description |
|------|------|-------------|
| 1 | Imports | Load required libraries |
| 2 | Tasks 1 & 2 | Simulate monthly stock prices using GBM; build `stock_prices` list |
| 3 | Task 3 | Create datetime index array (`dates`) using `pd.date_range` |
| 4 | Task 4 | Build `simulated_data` DataFrame with Date and Price columns |
| 5 | Task 5 | Compute monthly returns using `pct_change()` |
| 6 | Task 6 | Simulate market returns from $N(\mu_m/12,\ \sigma_m/\sqrt{12})$ |
| 7 | Task 7 | Add constant monthly risk-free rate (`annual_rf / 12`) |
| 8 | Task 8 | Compute excess returns: Stock Premium and Market Premium |
| 9 | Task 9 | Display first 5 rows of `simulated_data` |
| 10 | Task 10 | Fit CAPM regression via OLS and interpret results |
| 11 | Plots | Simulated price path and CAPM scatter plot |

---

## Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| `S0` | 50.0 | Initial stock price |
| `mu` | 0.10 | Annual expected return (10%) |
| `sigma` | 0.15 | Annual volatility (15%) |
| `dt` | 1 | Monthly time step |
| `n_steps` | 60 | Number of steps (5 years × 12 months) |
| `mu_m` | 0.08 | Market annual expected return (8%) |
| `sigma_m` | 0.10 | Market annual volatility (10%) |
| `annual_rf` | 0.04 | Annual risk-free rate (4%) |
| `random seed (stock)` | 42 | For reproducibility of stock simulation |
| `random seed (market)` | 7 | For reproducibility of market simulation |

---

## Key Results

| Metric | Value |
|--------|-------|
| Beta (β) | 0.1762 |
| Alpha (α) | −0.0023 |
| R² | 0.0189 (1.89%) |
| F-statistic p-value | 0.295 |

**Summary:** CAPM explains very little of the stock's return variation (R² = 1.89%).
Both α and β are statistically insignificant, which is expected given that the stock
and market returns were independently simulated with no built-in correlation.

---


