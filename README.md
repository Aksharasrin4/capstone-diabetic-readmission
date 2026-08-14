# Predicting and Prescribing Diabetic Patient Readmission Risk

**MS Business Analytics Capstone Project**  
**Author:** Akshara Miriyala  
**University:** University of Cincinnati — Carl H. Lindner College of Business  
**Program:** MS Business Analytics | BANA 7099 Capstone  
**First Reader:** Professor Robert Rooker  
**Term:** Spring 2026  

---

## Project Overview

This capstone project addresses one of the most costly and preventable problems 
in US healthcare — 30-day hospital readmissions among diabetic patients, costing 
over **$26 billion annually**.

Most healthcare analytics stops at prediction. This project goes further by asking:

> **"Which specific clinical decisions made at discharge most reduce a diabetic 
> patient's risk of returning within 30 days?"**

This shift from **prediction to prescription** is the core contribution of this project.

---

## Dataset

| Attribute | Details |
|-----------|---------|
| Source | UCI Machine Learning Repository |
| Link | https://archive.ics.uci.edu/dataset/296 |
| Paper | Strack et al. (2014), BioMed Research International |
| Raw Records | 101,766 patient encounters |
| After Deduplication | 71,515 unique patients |
| Features Used | 44 |
| Target Variable | Readmitted within 30 days (binary: 1/0) |
| Class Imbalance | 8.8% readmitted |

> ⚠️ The raw dataset is NOT included in this repository.  
> Download it directly from the UCI link above.

---

## Project Pipeline
Phase 1 → Data Loading & Cleaning
Phase 2 → Exploratory Data Analysis (7 plots)
Phase 3 → Feature Engineering & Train/Test Split
Phase 4 → Model Building (4 models)
Phase 5 → Evaluation & Variable Importance
Phase 6 → Prescriptive Clinical Recommendations

---

## Models Built & Results

| Model | AUC Score | Rank |
|-------|-----------|------|
| XGBoost | **0.6588** | 🥇 Best |
| Random Forest | 0.6480 | 2nd |
| Decision Tree | 0.6332 | 3rd |
| Logistic Regression | 0.6175 | Baseline |

All models evaluated on identical 70/30 stratified held-out test set  
with `random_state=42` for full reproducibility.

---

## Key Clinical Findings

### 1. Hospital Stay ≥ 5 Days → Enhanced Discharge Planning
Readmission risk rises from **6.4%** (1 day) to **12.0%** (8 days) — nearly doubles.

### 2. Mandate A1C Testing at Discharge
Patients not tested represent a missed opportunity to adjust treatment before leaving.

### 3. Insulin Reduction = Highest Readmission Risk
Patients whose insulin was **reduced** at discharge had the highest readmission  
rate of all groups at **10.3%** — higher than patients whose insulin was increased.

### 4. Polypharmacy Patients Need Pharmacist Review
20+ medications → **10.2%** readmission vs. **5.8%** for 1-5 medications.

---

## Repository Structure
---

## Tools & Technologies

![Python](https://img.shields.io/badge/Python-3.12-blue)
![sklearn](https://img.shields.io/badge/scikit--learn-latest-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-latest-green)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)

- **Python** — pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn
- **Models** — Logistic Regression, Decision Tree, Random Forest, XGBoost
- **Evaluation** — AUC-ROC, F1-score, Confusion Matrix, Partial Dependence Plots

---

## MS-BANA Curriculum Alignment

| Course | Concepts Applied |
|--------|-----------------|
| Data Mining I & II (BANA 7046/7047) | RF, XGBoost, AUC evaluation, tuning |
| Statistical Modeling | Logistic Regression, imbalance handling |
| Data Visualization | 14 publication-quality plots |
| Business Analytics Capstone | Prescriptive recommendations for stakeholders |

---

## How to Run

```bash
# 1. Clone this repository
git clone https://github.com/Aksharasrin4/capstone-diabetic-readmission.git

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn

# 3. Download the dataset from UCI and place in data/ folder
# https://archive.ics.uci.edu/dataset/296

# 4. Open the notebook
jupyter notebook capstone_diabetes.ipynb
```

---

## References

- Strack, B., et al. (2014). Impact of HbA1c Measurement on Hospital Readmission 
  Rates. *BioMed Research International.*
- UCI Machine Learning Repository. archive.ics.uci.edu/dataset/296
- Chen, T., & Guestrin, C. (2016). XGBoost. *KDD 2016.*
- Breiman, L. (2001). Random Forests. *Machine Learning, 45(1), 5-32.*

---

*Submitted in partial fulfillment of the requirements for the  
Master of Science in Business Analytics — University of Cincinnati*
