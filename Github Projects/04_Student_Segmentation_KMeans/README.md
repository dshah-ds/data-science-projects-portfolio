# Student Social Network Segmentation — K-Means Clustering

## Overview

An unsupervised machine learning project that segments **15,000 high school students** into distinct behavioural groups based on keyword mentions in their social network profiles — with no pre-defined labels.

The project demonstrates how K-Means clustering can turn raw, unlabelled data into actionable student welfare insights, including early identification of at-risk students.

## Business Problem

A school district wants to understand what kinds of students it has — not by grades, but by how they express themselves online. The goal is to:
- Identify natural student personas from social behaviour
- Prioritise welfare resources toward at-risk groups
- Design targeted programs for each segment

## Dataset

| Property | Value |
|---|---|
| File | `Clustering_Marketing.csv` |
| Rows | 15,000 student social network profiles |
| Features | 38 keyword mention counts (sports, music, fashion, religion, risk-related, etc.) |
| Labels | None (unsupervised — no pre-defined categories) |

**Feature Categories:**
- Sports: basketball, football, soccer, cheerleading, swimming, etc.
- Appearance: hair, dress, cute, hot, sexy, clothes
- Social Life: music, dance, rock, mall, shopping, kissed
- Religion: god, church, jesus, bible
- Fashion Brands: hollister, abercrombie
- Risk-Prone: drunk, drugs, die, death

## Methodology

```
Data Loading → Cleaning → StandardScaler → Hierarchical Clustering (exploratory)
→ Elbow Method → K-Means (K=4) → PCA Visualisation → Cluster Profiling → Insights
```

## Results

| Cluster | Label | Size | % | Key Signal |
|---|---|---|---|---|
| 0 | Fashion-Forward | ~432 | 3% | hollister, abercrombie, shopping, clothes |
| 1 | Silent Majority | ~10,520 | 70% | Low keyword counts across all categories |
| 2 | Actively Engaged | ~3,517 | 23% | Sports, music, dance, church |
| 3 | ⚠️ At-Risk Group | ~528 | 4% | drunk, drugs, die, death, sex |

**Silhouette Score (K=4):** Moderate — expected for high-dimensional, sparse keyword data.

## What This Project Covers

1. **Data Cleaning** — age outlier removal, keyword outlier detection, missing value imputation
2. **Feature Standardisation** — StandardScaler for equal feature contribution to distance
3. **Hierarchical Clustering** — dendrogram visualisation (3 linkage methods), silhouette analysis
4. **Elbow Method** — WCSS curve to determine optimal K
5. **K-Means Fitting** — K=4, n_init=10, silhouette score evaluation
6. **PCA Visualisation** — 2D projection of 38-dimensional cluster space
7. **Cumulative Variance Plot** — how many PCs are needed to explain 80% of variance
8. **Cluster Profiling** — mean keyword counts per cluster, category-level bar plots
9. **Business Recommendations** — actionable welfare and educational policy suggestions

## Key Business Finding

The most critical outcome is the identification of **Cluster 3 — the At-Risk Group (~528 students)**. These students exhibit high online activity dominated by risky keywords (drugs, drunk, death). This segment would be **nearly impossible to identify manually** across 15,000 profiles. K-Means clustering surfaces them automatically, enabling targeted counsellor outreach.

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
jupyter notebook Student_Segmentation_KMeans.ipynb
```

## Project Structure

```
04_Student_Segmentation_KMeans/
├── Student_Segmentation_KMeans.ipynb   # Full analysis notebook
├── Clustering_Marketing.csv             # Dataset
└── README.md                            # This file
```
