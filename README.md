# Insurance Renewal Prediction using XGBoost

## 📌 Project Overview
This project aims to predict whether a customer will renew their insurance policy using machine learning techniques. By analyzing behavioral, financial, and historical features, we train an XGBoost model to estimate renewal probabilities and segment customers by risk level. The goal is to help insurers identify high-risk customers and improve retention strategies.

## 📊 Dataset
- **Source**: Synthetic dataset modeled on real-world insurance attributes
- **Size**: Approximately 10,000 records
- **Features**:
  - Policy premium and claim amounts
  - Customer seniority and driving experience
  - Interaction with authorities and payment history
- **Preprocessing**:
  - Feature engineering (e.g., claim ratio, interaction score)
  - Date parsing and age calculation
  - Label encoding for categorical variables

## 🧠 Methods
We implemented and compared two models:
- ✅ **XGBoost**: Final model with high accuracy and robust performance
- ❌ **Logistic Regression**: Used as a baseline for comparison

### Feature Engineering Highlights
- `Claim_ratio`: Total claims divided by annual premium
- `Interaction_score`: Aggregated contact with authorities and witnesses
- `Customer_age`, `Driving_experience`, `Policy_tenure`: Derived from date fields
- `Payment_history_encoded`: Simulated and encoded payment behavior

## 📈 Model Evaluation

| Metric        | Value |
|---------------|-------|
| Accuracy      | 1.00  |
| ROC-AUC Score | 1.00  |
| F1-Score      | 1.00  |


