# Data Science Portfolio — Dev Shah

A collection of end-to-end data science projects covering **Statistics**, **Supervised Learning**, and **Unsupervised Learning**. Each project follows a full analytical pipeline — from raw data through cleaning, modelling, evaluation, and actionable business recommendations.

---

## Projects

### 01 · Statistical Analysis & Hypothesis Testing
**[US Customer Insights](./01_Statistics_Customer_Insights/)**

Exploratory data analysis and formal statistical hypothesis testing on 10,675 US retail customers. Answers real business questions about spending behaviour using t-tests, ANOVA, Chi-Square, and Pearson correlation.

| | |
|---|---|
| **Dataset** | 10,675 US customer records |
| **Techniques** | Descriptive statistics, data visualisation, bivariate analysis, hypothesis testing |
| **Key Finding** | Spending is uniform across gender, education, and state — but married customers with pets spend more |
| **Tools** | Python, pandas, scipy, seaborn |

---

### 02 · Multi-Model Classification — Healthcare
**[Renal Health Risk Prediction](./02_Renal_Risk_Classification/)**

Predicts kidney disease risk from clinical patient data by training and comparing five machine learning models. Includes full hyperparameter tuning and optimal threshold selection.

| | |
|---|---|
| **Dataset** | 20,000 clinical patient records (13,847 after cleaning) |
| **Techniques** | Logistic Regression, KNN, Decision Tree, Random Forest, GridSearchCV, ROC-AUC optimisation |
| **Best Model** | Random Forest — ROC-AUC 0.8257 |
| **Key Finding** | GFR value and creatinine level are the strongest clinical predictors of renal risk |
| **Tools** | Python, scikit-learn, statsmodels, pandas |

---

### 03 · Linear Regression — Marketing Analytics
**[Advertising Budget & Sales Prediction](./03_Advertising_Linear_Regression/)**

Quantifies the impact of TV, Radio, and Newspaper advertising budgets on product sales using multiple linear regression. Identifies which channels drive ROI and which are wasting budget.

| | |
|---|---|
| **Dataset** | 200 market observations (ISLR Advertising dataset) |
| **Techniques** | Simple & multiple linear regression, VIF multicollinearity check, OLS statistical testing, residual diagnostics |
| **Best Model** | TV + Radio — Test R² = 0.89, RMSE ≈ 1,030 units |
| **Key Finding** | Newspaper spend is statistically insignificant — TV and Radio alone explain 89% of sales variance |
| **Tools** | Python, scikit-learn, statsmodels, seaborn |

---

### 04 · Unsupervised Learning — Education Analytics
**[Student Social Network Segmentation](./04_Student_Segmentation_KMeans/)**

Segments 15,000 high school students into behavioural clusters using K-Means, based entirely on keyword mentions in their social network profiles — with no pre-defined labels. Identifies an at-risk student group that would be impossible to flag manually.

| | |
|---|---|
| **Dataset** | 15,000 student social network keyword profiles (38 features) |
| **Techniques** | K-Means clustering, hierarchical clustering, Elbow Method, PCA visualisation, silhouette scoring |
| **Clusters Found** | 4 — Fashion-Forward (3%), Silent Majority (70%), Actively Engaged (23%), At-Risk Group (4%) |
| **Key Finding** | 528 students flagged in the At-Risk cluster — the highest welfare priority |
| **Tools** | Python, scikit-learn, scipy, seaborn |

---

## Skills Demonstrated

| Area | Techniques |
|---|---|
| **Statistics** | Descriptive stats, hypothesis testing (t-test, ANOVA, Chi-Square, Pearson), confidence intervals |
| **Supervised — Classification** | Logistic Regression, KNN, Decision Tree, Random Forest, GridSearchCV, ROC-AUC |
| **Supervised — Regression** | Linear Regression, OLS, VIF, residual diagnostics, feature selection |
| **Unsupervised** | K-Means, Hierarchical Clustering, Elbow Method, PCA, Silhouette Score |
| **Data Preparation** | Missing value imputation, outlier detection & clipping, StandardScaler, train/test split |
| **Visualisation** | Histograms, boxplots, scatter plots, heatmaps, KDE, dendrograms, PCA scatter |

---

## Setup

Each project folder is self-contained with its own dataset and `README.md`. To run any notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels scipy openpyxl
cd <project_folder>
jupyter notebook
```

---

*Built as part of the Adda247 December Data Science batch.*
