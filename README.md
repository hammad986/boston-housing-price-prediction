# 🏡 Boston Housing Price Prediction & Predictive Regression Modeling

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.2+-orange.svg)](https://scikit-learn.org/)
[![Domain](https://img.shields.io/badge/Domain-Real%20Estate%20Analytics%20%7C%20Econometrics-darkblue.svg)](#overview)
[![Task](https://img.shields.io/badge/Task-Supervised%20Regression-success.svg)](#model-development)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)

---

## 📌 Executive Overview
Real estate valuation is influenced by an intricate web of socio-economic, environmental, and structural factors. For homebuyers, property developers, and mortgage lenders, establishing accurate appraisal values prevents capital misallocation and informs fair credit issuance.

This project implements an end-to-end **Predictive Regression Modeling** pipeline to forecast median home values (`MEDV` in $1000s) based on demographic, architectural, and geographic characteristics across residential suburbs.

---

## 🎯 Key Business & Valuation Objectives
- **Accurate Property Valuation:** Benchmark fair market prices using multi-variable statistical regression rather than subjective appraisals.
- **Urban Planning & Investment Insights:** Identify neighborhood factors (e.g., student-teacher ratios, air quality, crime rates) that exert the strongest positive or negative drag on property equity.
- **Risk Assessment for Lending:** Provide banks and mortgage underwriters with data-backed collateral price estimates.

---

## 🔬 Dataset Schema & Feature Dictionary
The dataset contains 14 standardized suburban attributes:

| Feature | Description | Expected Impact on Price |
|---|---|---|
| `CRIM` | Per capita crime rate by town | Negative correlation |
| `ZN` | Proportion of residential land zoned for lots over 25,000 sq.ft. | Positive correlation |
| `INDUS` | Proportion of non-retail business acres per town | Negative correlation |
| `CHAS` | Charles River dummy variable (= 1 if tract bounds river; 0 otherwise) | Positive premium |
| `NOX` | Nitric oxides concentration (parts per 10 million) | Negative correlation |
| `RM` | Average number of rooms per dwelling | Strong positive correlation |
| `AGE` | Proportion of owner-occupied units built prior to 1940 | Variable |
| `DIS` | Weighted distances to five employment centers | Positive accessibility |
| `RAD` | Index of accessibility to radial highways | Transport connectivity |
| `TAX` | Full-value property-tax rate per $10,000 | Carrying cost drag |
| `PTRATIO` | Pupil-teacher ratio by town school district | Strong negative correlation |
| `B` | Proportion of population metric | Demographic factor |
| `LSTAT` | % lower status of the population | Strong negative correlation |
| **`MEDV`** | **Median value of owner-occupied homes ($1000's)** | **Target Variable** |

---

## ⚙️ Model Development & Benchmarking
Three supervised regression architectures were trained and cross-validated:

```
[Cleaned Housing Dataset]
            │
            ▼
[Exploratory Data Analysis]
 ├── Distribution Plots (Histograms & KDE)
 ├── Correlation Heatmap Matrix
 └── Scatter Plots (RM vs MEDV, LSTAT vs MEDV)
            │
            ▼
[Data Partitioning (Train/Test Split)]
            │
            ▼
[Model Training & Comparative Benchmark]
 ├── Linear Regression (Standard OLS baseline)
 ├── Decision Tree Regressor (Non-linear recursive partitioning)
 └── Random Forest Regressor (Ensemble bagging of regression trees)
            │
            ▼
[Diagnostics & Evaluation Metrics]
 ├── Root Mean Squared Error (RMSE)
 ├── Mean Absolute Error (MAE)
 └── Coefficient of Determination (R²)
```

---

## 🏆 Key Findings & Model Performance
- **Primary Price Drivers:** Average rooms per dwelling (`RM`) and socioeconomic status index (`LSTAT`) account for over 70% of price variance.
- **Ensemble Superiority:** The **Random Forest Regressor** achieved superior predictive accuracy compared to standard OLS Linear Regression, effectively dampening outlier sensitivity and capturing non-linear interactions between school quality (`PTRATIO`) and highway proximity (`RAD`).

---

## 📁 Repository Structure
```
Boston-Housing-Price-Prediction/
├── Regression_predict_model.ipynb      # Complete analysis, training, and evaluation notebook
├── cleaned_house_data.csv              # Cleaned housing dataset
├── eda_visualizations.png              # Exploratory data analysis visualization grid
├── feature_importance.png              # Feature importance ranking plot
├── model_performance.png               # Regression model performance comparison chart
├── requirements.txt                    # Project Python dependencies
├── .gitignore                          # Git tracking rules
└── README.md                           # Documentation
```

---

## 🚀 Quickstart Guide

### 1. Installation
```bash
git clone https://github.com/<your-username>/Boston-Housing-Price-Prediction.git
cd Boston-Housing-Price-Prediction
pip install -r requirements.txt
```

### 2. Run Notebook
```bash
jupyter notebook Regression_predict_model.ipynb
```

---

## 👤 Author & Acknowledgments
- **Author:** Muhammed Hammad S
- **License:** MIT License
