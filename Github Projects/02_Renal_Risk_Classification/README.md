# Renal Health Risk Prediction — Multi-Model Classification

## Overview

A healthcare analytics project that builds and compares **five machine learning models** to predict renal (kidney) disease risk in patients. Uses a dataset of 20,000 anonymised clinical records to demonstrate the full supervised learning pipeline — from raw data through feature engineering, model training, hyperparameter tuning, and final selection.

## Business Problem

Renal disorders progress silently and are often diagnosed too late. This model serves as an **early-warning screening system** that helps:
- Clinicians prioritise high-risk patients for further investigation
- Hospitals optimise diagnostic resource allocation
- Insurance providers assess risk-adjusted premiums

## Dataset

| Property | Value |
|---|---|
| File | `RNRC.xlsx` |
| Original Rows | 20,000 |
| Cleaned Rows | 13,847 (after removing 6,153 duplicates) |
| Features | 25 clinical + demographic |
| Target | `renal_risk_flag` (Binary: 0/1) |
| Class Balance | 52% No Risk / 48% At Risk |

### Key Features
- Clinical: `creatinine_level`, `gfr_value`, `albumin_level`, `bun_level`, `glucose_level`
- Vitals: `bp_level`, `wbc_count`, `rbc_count`, `cell_volume_pct`
- Comorbidities: `diabetes_mell_flag`, `heart_issue_flag`, `anemia_flag`
- Demographics: `age_years`, `gender_code`

## Models & Results

| Model | Accuracy | F1 Score | ROC-AUC |
|---|---|---|---|
| Logistic Regression (statsmodels) | 70.65% | 0.7120 | 0.7647 |
| Logistic Regression (sklearn tuned) | 70.87% | 0.7062 | 0.7645 |
| K-Nearest Neighbours (tuned) | 72.53% | 0.7164 | 0.7790 |
| Decision Tree (tuned) | 74.62% | 0.7573 | 0.8063 |
| **Random Forest (tuned)** | **73.75%** | **0.7282** | **0.8257** |

**Best Model: Random Forest** (highest ROC-AUC — the most relevant metric for medical screening).

## Techniques Demonstrated

- **Missing value imputation** (median strategy)
- **Duplicate detection and removal**
- **Feature selection** via p-values (statsmodels) and VIF analysis
- **Optimal decision threshold selection** using Youden's J statistic
- **GridSearchCV** for hyperparameter tuning (all four sklearn models)
- **Cross-validation** (5-fold)
- **Model evaluation**: Accuracy, F1 Score, ROC-AUC, Confusion Matrix, Classification Report

## Key Clinical Findings

The strongest predictors of renal risk align with established medical literature:
1. **GFR Value** — glomerular filtration rate (strongest predictor, coef = +0.77)
2. **Creatinine Level** — kidney function marker (coef = +0.53)
3. **Albumin Level** — protein loss indicator (coef = +0.14)
4. **Diabetes Mellitus** and **Heart Disease flags** — key comorbidities

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels openpyxl
jupyter notebook Renal_Risk_Prediction.ipynb
```

## Project Structure

```
02_Renal_Risk_Classification/
├── Renal_Risk_Prediction.ipynb   # Full analysis notebook
├── RNRC.xlsx                     # Dataset
└── README.md                     # This file
```
