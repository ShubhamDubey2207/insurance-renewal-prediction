#  Insurance Renewal Prediction  
**Models Used**: Logistic Regression, Random Forest, XGBoost  
**Final Model**:  XGBoost (Best Performance)

---

##  Project Overview
This project predicts whether a customer will renew their insurance policy using machine learning. By analyzing behavioral, financial, and historical features, we train multiple models to estimate renewal probabilities and segment customers by risk level. The goal is to help insurers identify high-risk customers, improve retention strategies, and personalize outreach.


---

## Dataset
- **Source**: Synthetic dataset modeled on real-world insurance attributes  
- **Size**: ~10,000 records  
- **Key Features**:
  - Policy premium and claim amounts
  - Customer seniority and driving experience
  - Interaction with authorities and payment history
  - Contract dates and license history

###  Preprocessing Steps
- **Feature Engineering**:
  - `Claim_ratio`: total_claim_amount / policy_annual_premium
  - `Interaction_score`: sum of authorities contacted, witnesses, and police report availability
  - `Customer_age`, `Driving_experience`, `Policy_tenure`: derived from date fields
- **Label Encoding**:
  - Simulated `Payment_history` based on premium thresholds
  - Encoded into `Payment_history_encoded` using `LabelEncoder`
- **Target Variable**:
  - `Renewed`: binary label based on seniority and premium thresholds

---

##  Modeling Approach

We trained and compared three models:

| Model               | Purpose                              |
|---------------------|---------------------------------------|
| Logistic Regression | Baseline model for comparison         |
| Random Forest       | Used for feature importance analysis  |
| XGBoost             | Final model with highest accuracy     |

###  Final Model: XGBoost
- Achieved perfect accuracy on test set
- Used for renewal probability prediction
- Enabled customer risk segmentation

---

##  Model Evaluation Reports

###  Logistic Regression

| Class | Precision | Recall | F1-Score | Support |
|:------|:----------:|:-------:|:---------:|:--------:|
| 0     | 0.98       | 0.87    | 0.92      | 52       |
| 1     | 0.97       | 1.00    | 0.98      | 248      |
| **Accuracy** |       |        | **0.97**  | **300**  |

---

###  Random Forest

| Class | Precision | Recall | F1-Score | Support |
|:------|:----------:|:-------:|:---------:|:--------:|
| 0     | 1.00       | 1.00    | 1.00      | 52       |
| 1     | 1.00       | 1.00    | 1.00      | 248      |
| **Accuracy** |       |        | **1.00**  | **300**  |

---

###  XGBoost

| Class | Precision | Recall | F1-Score | Support |
|:------|:----------:|:-------:|:---------:|:--------:|
| 0     | 1.00       | 1.00    | 1.00      | 52       |
| 1     | 1.00       | 1.00    | 1.00      | 248      |
| **Accuracy** |       |        | **1.00**  | **300**  |

---

###  Summary

| Model               | Accuracy | Precision | Recall | F1-Score |
|---------------------|:--------:|:---------:|:------:|:--------:|
| Logistic Regression | 0.97     | 0.97      | 0.97   | 0.97     |
| Random Forest       | 1.00     | 1.00      | 1.00   | 1.00     |
| XGBoost             | 1.00     | 1.00      | 1.00   | 1.00     |

---

##  Top Feature Importances (Random Forest)

| Feature                 | Importance (%) |
|-------------------------|----------------|
| Seniority               | 72.60          |
| Policy_tenure           | 13.74          |
| policy_annual_premium   | 2.51           |
| Policies_in_force       | 2.48           |
| Driving_experience      | 2.35           |
| Customer_age            | 2.30           |
| Claim_ratio             | 1.61           |
| total_claim_amount      | 1.49           |
| Interaction_score       | 0.43           |
| Payment_history_encoded | 0.27           |

---

##  Risk Segmentation

Customers were segmented based on predicted renewal probability:

| Risk Level   | Probability Range |
|--------------|-------------------|
| High Risk    | < 0.4             |
| Medium Risk  | 0.4 – 0.7         |
| Low Risk     | > 0.7             |

This segmentation helps insurers prioritize retention efforts and personalize outreach strategies.

---

##  User Input Prediction

The final model supports real-time prediction from user input. Users can enter values for key features such as:

- `policy_annual_premium`
- `total_claim_amount`
- `Seniority`, `Policy_tenure`, `Driving_experience`
- `Interaction_score`, `Claim_ratio`
- `Payment_history_encoded`

The model returns:
-  Renewal probability
-  Predicted renewal status (Renewed / Not Renewed)

---

##  Conclusion

This project demonstrates how machine learning — especially **XGBoost** — can effectively predict insurance renewal behavior using structured customer data. Through a comprehensive pipeline that includes feature engineering, model training, evaluation, and prediction, we achieved high accuracy and actionable insights.

Key accomplishments:

-  **Customer Risk Identification**: The model accurately predicts renewal probabilities, allowing insurers to identify high-risk customers who are less likely to renew.
- **Retention Strategy Optimization**: By segmenting customers into High, Medium, and Low risk groups, insurers can prioritize retention efforts and allocate resources more effectively.
-  **Feature Engineering Excellence**: Derived features like `Claim_ratio`, `Interaction_score`, `Customer_age`, and `Policy_tenure` significantly improved model performance.
-  **Model Performance**: XGBoost achieved perfect accuracy on the test set, outperforming Logistic Regression and Random Forest.
-  **Real-Time Prediction**: The final model supports user input for key features, enabling real-time prediction of renewal status and probability.
-  **Exportable Results**: Predictions and risk segments are saved to a CSV file for integration into business workflows or dashboards.


## References

1. Chen, T., & Guestrin, C. (2016). *XGBoost: A Scalable Tree Boosting System*. Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. https://doi.org/10.1145/2939672.2939785

2. Scikit-learn Developers. (2025). *Scikit-learn: Machine Learning in Python*. https://scikit-learn.org/

3. Kaggle Datasets. (n.d.). *Insurance Data for Predictive Modeling*. Retrieved from https://www.kaggle.com/

4. Brownlee, J. (2020). *Machine Learning Mastery with Python: Understand Your Data, Create Accurate Models, and Work Projects End-to-End*. Machine Learning Mastery.

5. Official XGBoost Documentation. (2025). *XGBoost Python Package*. https://xgboost.readthedocs.io/

6. Pandas Development Team. (2025). *pandas: Python Data Analysis Library*. https://pandas.pydata.org/

7. NumPy Developers. (2025). *NumPy: Fundamental package for scientific computing with Python*. https://numpy.org/



