# Statistical Analysis & Hypothesis Testing — US Customer Insights

## Project Overview

This project performs a full end-to-end statistical analysis on a dataset of **10,675 US customers**, combining descriptive statistics, data visualization, bivariate analysis, and formal hypothesis testing to extract actionable business insights.

## Business Problem

A retail company wants to understand its customer base better — how old they are, how much they spend, whether demographic factors (gender, education, state) actually drive spending differences, and whether engagement patterns vary by customer type. This analysis answers those questions using statistical rigor rather than gut instinct.

## Dataset

| Property | Details |
|---|---|
| File | `US_Customer_Insights_Dataset.csv` |
| Rows | 10,675 |
| Columns | 12 |
| Source | Synthetic US retail customer dataset |

**Key Features:**
- `Age` — Customer age (18–80)
- `Gender` — Male / Female / Non-Binary
- `Education` — High School / Associate / Bachelor / Master / PhD
- `State` — 10 US states
- `Married` — Yes / No
- `NumPets` — Number of pets owned (0–4)
- `MonthlySpend` — Monthly spending in USD
- `DaysSinceLastInteraction` — Recency of last engagement

## What This Project Covers

### 1. Data Exploration
- Dataset shape, data types, null value check, duplicate detection
- Distinguishing categorical vs. numerical features

### 2. Descriptive Statistics
- Mean, median, standard deviation for all numerical fields
- Mode and frequency counts for categorical variables
- Min/Max analysis

### 3. Data Visualization
- Histograms and boxplots (Age, MonthlySpend)
- Bar charts (Gender, Education, State)
- Scatter plot: Age vs. MonthlySpend
- KDE plots: Spending by education level and marital status

### 4. Bivariate Analysis
- Pearson correlation matrix heatmap
- Crosstab: Gender × Marital Status
- Grouped statistics: Average MonthlySpend by State, Education, Gender

### 5. Hypothesis Testing
| Test | Question |
|---|---|
| Independent t-test | Do males and females spend differently? |
| One-Way ANOVA | Does education level impact monthly spend? |
| Chi-Square Test | Is marital status related to number of pets? |
| Pearson Correlation | Are older people less active (DaysSinceLastInteraction)? |
| One-Way ANOVA | Does state-wise spend vary significantly? |

## Key Findings

- **Spending is uniform** across gender, education level, and state — no significant differences found in any of the four tests
- **Marital status and pet ownership are significantly associated** (χ² = 177.6, p ≈ 0) — married customers tend to own more pets
- **Monthly spend is right-skewed** with a small group of high spenders pulling the mean above the median
- **Age has zero relationship with engagement** (r = −0.004, p = 0.68)
- A **VIP/loyalty tier for customers spending >$500/month** is the most data-supported business opportunity

## Tech Stack

- Python 3
- pandas, numpy
- matplotlib, seaborn
- scipy.stats

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scipy
jupyter notebook US_Customer_Insights_Analysis.ipynb
```

## Project Structure

```
01_Statistics_Customer_Insights/
├── US_Customer_Insights_Analysis.ipynb   # Main analysis notebook
├── US_Customer_Insights_Dataset.csv      # Dataset
└── README.md                             # This file
```
