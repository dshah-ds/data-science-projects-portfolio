# Advertising Budget & Sales Revenue Prediction — Linear Regression

## Overview

A marketing analytics project that uses **Multiple Linear Regression** to quantify the impact of TV, Radio, and Newspaper advertising budgets on product sales. Built to answer a core business question: *which advertising channel gives the best return on investment?*

## Business Problem

A consumer goods company wants to optimise its advertising spend across three channels. The model tells them:
- Which channels actually drive sales (statistical significance)
- How much sales increase per dollar spent on each channel
- Which channels are wasting budget with no measurable impact

## Dataset

| Property | Value |
|---|---|
| File | `Advertising.csv` |
| Rows | 200 |
| Features | TV, Radio, Newspaper (budgets in $000s) |
| Target | Sales (units in 000s) |
| Source | ISLR (Introduction to Statistical Learning) |

## Key Results

| Model | Features | Test R² | Test RMSE |
|---|---|---|---|
| Simple LR | TV only | ~0.60 | ~1.97 |
| Simple LR | Radio only | ~0.32 | ~2.57 |
| Simple LR | Newspaper only | ~0.04 | ~3.07 |
| Multiple LR | TV + Radio + Newspaper | ~0.89 | ~1.03 |
| **Final LR** | **TV + Radio** | **~0.89** | **~1.03** |

## What This Project Covers

1. **Exploratory Data Analysis** — distributions, boxplots, scatter plots with trend lines, pairplot
2. **Correlation Analysis** — Pearson heatmap showing TV (r=0.78), Radio (r=0.58), Newspaper (r=0.23)
3. **Multicollinearity Check** — VIF analysis confirming no multicollinearity between features
4. **Data Preprocessing** — IQR outlier clipping, StandardScaler (fit on train only)
5. **Simple Linear Regression** — baseline for each channel independently
6. **Multiple Linear Regression** — all channels, then final model without Newspaper
7. **Statistical Significance Testing** — statsmodels OLS with p-values, t-stats, F-statistic
8. **Model Evaluation** — R², RMSE, MAE, Actual vs Predicted plots
9. **Residual Diagnostics** — residuals vs fitted, histogram, Q-Q plot

## Key Findings

- **TV + Radio explain 89% of variance in sales** — a highly effective model
- **Newspaper is statistically insignificant** (p > 0.05) once TV and Radio are in the model — budget here is wasted
- **TV is the primary driver** (highest coefficient); Radio provides strong incremental lift
- Residuals are approximately normally distributed with no severe heteroscedasticity

## Business Recommendations

1. **TV** should remain the anchor channel — highest ROI per dollar
2. **Pair TV with Radio** for maximum sales lift — the combination is synergistic
3. **Reallocate Newspaper budget** to TV or Radio — zero marginal impact detected
4. Use the model as a **budget simulation tool** to forecast sales for any proposed spend mix

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels
jupyter notebook Advertising_Linear_Regression.ipynb
```

## Project Structure

```
03_Advertising_Linear_Regression/
├── Advertising_Linear_Regression.ipynb   # Full analysis notebook
├── Advertising.csv                        # Dataset
└── README.md                              # This file
```
