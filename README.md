# Heart Failure Mortality Prediction

## Overview
End-to-end machine learning project predicting 30-day mortality in heart failure 
patients using clinical records. Built as part of a healthcare data science portfolio.

**Dataset:** Heart Failure Clinical Records (Kaggle) — 299 patients, 13 features  
**Target:** DEATH_EVENT (binary — survived vs died)  
**Best Model:** Random Forest — AUC 0.772 (leakage-free)

---

## Key Findings
- `creatinine_ef_ratio` (engineered feature) was the strongest predictor
- `serum_creatinine` and `ejection_fraction` confirmed as top clinical predictors
- `time` (follow-up period)


cat > '/Users/sunnybhupati/sunny_projects/Claude Co work - Skew/heart-failure-prediction/README.md' << 'EOF'
# Heart Failure Mortality Prediction

## Overview
End-to-end machine learning project predicting 30-day mortality in heart failure 
patients using clinical records. Built as part of a healthcare data science portfolio.

**Dataset:** Heart Failure Clinical Records (Kaggle) — 299 patients, 13 features  
**Target:** DEATH_EVENT (binary — survived vs died)  
**Best Model:** Random Forest — AUC 0.772 (leakage-free)

---

## Key Findings
- `creatinine_ef_ratio` (engineered feature) was the strongest predictor
- `serum_creatinine` and `ejection_fraction` confirmed as top clinical predictors
- `time` (follow-up period) caused data leakage — removed for a clinically honest model
- Random Forest outperformed Logistic Regression and XGBoost on this small dataset

---

## Model Comparison

| Model | AUC-ROC | Died Recall | Note |
|---|---|---|---|
| Logistic Regression | 0.882 | 0.58 | Leaky (includes time) |
| LR Balanced | 0.872 | 0.63 | Leaky (includes time) |
| Random Forest | 0.884 | 0.68 | Leaky (includes time) |
| XGBoost | 0.843 | 0.58 | Leaky (includes time) |
| **RF — No Time** | **0.772** | **0.42** | **Final model — leakage-free** |

---

## Tech Stack
- Python 3, Jupyter Notebook
- pandas, numpy, matplotlib
- scikit-learn, xgboost, shap

---

## Background
Built by Sunny Bhupati — Data Architect at Oracle Health (Cerner).  
Part of a hands-on healthcare data science learning portfolio.  
GitHub: https://github.com/sunnybhupatigit/My-Projects
