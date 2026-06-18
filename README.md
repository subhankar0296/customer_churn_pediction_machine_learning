# 📊 Customer Churn Prediction

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Business Overview
Customer churn is one of the most critical metrics for subscription-based businesses. Acquiring a new customer is significantly more expensive than retaining an existing one. This project develops an end-to-end machine learning pipeline to proactively identify at-risk customers, enabling data-driven retention marketing campaigns and reducing revenue leakage.

---

## 🛠️ Technical Stack & Tools
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn
* **Hyperparameter Tuning:** GridSearchCV

---

## 🚀 Key Features & Pipeline Architecture

### 1. Robust Data Preprocessing & Cleaning
* **Anomaly Resolution:** Handled whitespace anomalies and type coercion in features like `TotalCharges`.
* **Missing Value Imputation:** Fixed structural missingness using median imputation strategies to preserve dataset integrity.
* **Feature Transformation:** Applied `StandardScaler` to continuous features and robust encoding to categorical variables, ensuring strict isolation to prevent data leakage during cross-validation.

### 2. Model Development & Hyperparameter Tuning
* **Algorithm:** Random Forest Classifier.
* **Class Imbalance Strategy:** Integrated `class_weight='balanced'` within the model architecture to robustly address minority class underrepresentation.
* **Optimization:** Leveraged `GridSearchCV` with Stratified K-Fold cross-validation, intentionally optimizing for **Recall** to minimize critical False Negatives.

---

## 📈 Model Performance Metrics

Because missing a customer who is about to churn (False Negative) is highly expensive for the business, **Recall** was selected as our primary optimization metric.

| Metric | Score | Implication |
| :--- | :--- | :--- |
| **Recall** | **79%** | Successfully captures 79% of all actual churning customers. |
| **ROC-AUC** | **83%** | Demonstrates strong model discrimination power between churners and loyal customers. |

---

## 🔬 Core Insights & Key Decision Drivers
Through the model's feature importance extraction, the top driving factors for customer churn were identified as:
1. **Contract Type:** Month-to-month contracts showed significantly higher churn propensity compared to 1- or 2-year commitments.
2. **Tenure:** Customer risk drops exponentially after the first 6–12 months of the lifecycle.
3. **Payment Method:** Electronic check users exhibited a higher correlation with churn compared to automated payment methods.

---

