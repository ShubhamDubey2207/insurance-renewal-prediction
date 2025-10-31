# 🧠 Insurance Renewal Prediction  
**Models Used**: Logistic Regression, Random Forest, XGBoost

## 📌 Project Overview
This project predicts whether a customer will renew their insurance policy using machine learning. By analyzing behavioral, financial, and historical features, we train multiple models to estimate renewal probabilities and segment customers by risk level. The goal is to help insurers identify high-risk customers and improve retention strategies.

---

## 📊 Dataset
- **Source**: Synthetic dataset modeled on real-world insurance attributes
- **Size**: ~10,000 records
- **Features**:
  - Policy premium and claim amounts
  - Customer seniority and driving experience
  - Interaction with authorities and payment history
- **Preprocessing**:
  - Feature engineering (`Claim_ratio`, `Interaction_score`)
  - Date parsing to derive age, tenure, experience
  - Label encoding for categorical variables

---

## 🧠 Methods
We implemented and compared three models:
- ✅ **XGBoost**: Final model with perfect accuracy and robust performance
- ✅ **Random Forest**: Used for feature importance analysis
- ❌ **Logistic Regression**: Baseline model for comparison

### Feature Engineering Highlights
- `Claim_ratio`: Total claims divided by annual premium
- `Interaction_score`: Aggregated contact with authorities and witnesses
- `Customer_age`, `Driving_experience`, `Policy_tenure`: Derived from date fields
- `Payment_history_encoded`: Simulated and encoded payment behavior

---

# 📈 Model Evaluation Reports

This document summarizes the performance of three machine learning models: **Logistic Regression**, **Random Forest**, and **XGBoost**.

---

### 📊 Logistic Regression Report

| Class | Precision | Recall | F1-Score | Support |
|:------|:----------:|:-------:|:---------:|:--------:|
| 0 | 0.98 | 0.87 | 0.92 | 52 |
| 1 | 0.97 | 1.00 | 0.98 | 248 |
| **Accuracy** |  |  | **0.97** | **300** |
| **Macro Avg** | 0.98 | 0.93 | 0.95 | 300 |
| **Weighted Avg** | 0.97 | 0.97 | 0.97 | 300 |

---

### 🌲 Random Forest Report

| Class | Precision | Recall | F1-Score | Support |
|:------|:----------:|:-------:|:---------:|:--------:|
| 0 | 1.00 | 1.00 | 1.00 | 52 |
| 1 | 1.00 | 1.00 | 1.00 | 248 |
| **Accuracy** |  |  | **1.00** | **300** |
| **Macro Avg** | 1.00 | 1.00 | 1.00 | 300 |
| **Weighted Avg** | 1.00 | 1.00 | 1.00 | 300 |

---

### ⚡ XGBoost Report

| Class | Precision | Recall | F1-Score | Support |
|:------|:----------:|:-------:|:---------:|:--------:|
| 0 | 1.00 | 1.00 | 1.00 | 52 |
| 1 | 1.00 | 1.00 | 1.00 | 248 |
| **Accuracy** |  |  | **1.00** | **300** |
| **Macro Avg** | 1.00 | 1.00 | 1.00 | 300 |
| **Weighted Avg** | 1.00 | 1.00 | 1.00 | 300 |

---

### 🧾 Summary
| Model | Accuracy | Precision | Recall | F1-Score |
|:------|:----------:|:----------:|:--------:|:----------:|
| Logistic Regression | 0.97 | 0.97 | 0.97 | 0.97 |
| Random Forest | 1.00 | 1.00 | 1.00 | 1.00 |
| XGBoost | 1.00 | 1.00 | 1.00 | 1.00 |

---


---

### 🔝 Top Feature Importances (Random Forest)

| Feature                   | Importance (%) |
|---------------------------|----------------|
| Seniority                 | 72.60          |
| Policy_tenure             | 13.74          |
| policy_annual_premium     | 2.51           |
| Policies_in_force         | 2.48           |
| Driving_experience        | 2.35           |
| Customer_age              | 2.30           |
| Claim_ratio               | 1.61           |
| total_claim_amount        | 1.49           |
| Interaction_score         | 0.43           |
| Payment_history_encoded   | 0.27           |

---

## 🔍 Risk Segmentation

Customers were segmented based on predicted renewal probability:

- **High Risk**: < 0.4  
- **Medium Risk**: 0.4 – 0.7  
- **Low Risk**: > 0.7  

This segmentation helps insurers prioritize retention efforts and personalize outreach strategies.

---

## ✅ Conclusion

This project demonstrates how machine learning — especially **XGBoost** — can effectively predict insurance renewal behavior. With perfect accuracy on the test set, the model enables insurers to:

- 🔍 Identify at-risk customers  
- 📊 Prioritize retention strategies  
- 📣 Optimize marketing and outreach  

The pipeline includes feature engineering, model training, risk segmentation, and prediction export — making it ready for deployment or integration into business workflows.
