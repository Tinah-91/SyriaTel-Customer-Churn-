# SyriaTel Customer Churn Prediction

Predicting which customers are likely to leave SyriaTel’s telecom services using machine learning.

**Author** by [Tinah Ngei](https://github.com/Tinah-91)

## Project Overview

Customer churn is a critical metric for telecom providers like SyriaTel. This project aims to develop machine learning models that predict whether a customer will churn based on their usage patterns and plan details. Predicting churn helps the company take proactive measures, reduce loss, and enhance customer satisfaction.

---

## Business Objective

- Identify **customers likely to churn**
- Enable **targeted retention strategies**
- Minimize customer loss and maximize revenue

---

## Data Understanding

The dataset consists of 3,333 customer records with 20+ features, including:

- **Customer Plan Details**: International Plan, Voice Mail Plan
- **Usage Stats**: Total Day/Evening/Night/International Minutes and Charges
- **Customer Service Interactions**
- **Location**: State

The target variable is `churn` (Yes/No).

---

## Data Preparation

- Converted categorical features using **One-Hot Encoding**
- Scaled numerical features using **StandardScaler**
- Addressed class imbalance via **Stratified Train-Test Split (80/20)**
- Checked for missing values and data types

---

## Exploratory Data Analysis (EDA)

We explored:

- **Churn distribution across States**
- Relationship between **customer service calls and churn**
- Impact of **international plan** on churn

### Recommended Plots for `images/` folder

1. `churn_distribution.png` – Overall churn vs non-churn
2. `churn_by_state_top20.png` – Top 20 states by churn
3. `churn_by_service_calls.png` – Service calls vs churn
4. `heatmap_correlations.png` – Feature correlation matrix

---

## Machine Learning

We used and compared **5 classification models**:

| Model                 | Notes                          |
|----------------------|--------------------------------|
| Logistic Regression  | Baseline linear classifier     |
| K-Nearest Neighbors  | Instance-based learning        |
| Support Vector Machine (SVM) | Effective in high-dimensional space |
| Random Forest Classifier | Ensemble decision trees     |
| XGBoost              | High-performance gradient boosting |

Each model was trained using the same preprocessed dataset and evaluated using:

- **Confusion Matrix**
- **ROC Curve & AUC**
- **Classification Report** (Accuracy, Precision, Recall, F1-Score)

### Suggested Image Exports:
- `conf_matrix_all_models.png`
- `roc_curves_all_models.png`
- `model_scores_comparison.png`

---

### Evaluation Summary

| Model               | Accuracy | Precision | Recall  | F1-Score | AUC     |
|--------------------|----------|-----------|---------|----------|---------|
| **XGBoost**         | 94.90%   | 88.89%    | 74.23% | 80.90%   | 88.95%  |
| Random Forest       | 93.25%   | 91.94%    | 58.76% | 71.70%   | 88.92%  |
| Logistic Regression | 86.36%   | 56.52%    | 26.80% | 36.36%   | 80.15%  |
| SVM                 | 87.41%   | 80.95%    | 17.53% | 28.81%   | 86.54%  |
| KNN                 | 85.46%   | 50.00%    | 5.15%  | 9.35%    | 67.10%  |

✅ **XGBoost achieved the highest AUC and F1-Score**, making it the best-performing model for this churn prediction task.

---

## Recommendations

- **Customers with many service calls** should be flagged for proactive engagement.
- **Users with international plans** show a higher churn rate — revise plan benefits or offer loyalty incentives.
- Target marketing efforts in **top churn-prone states**.

---

## Next Steps

- Integrate churn model into SyriaTel’s CRM for live scoring
- Conduct **A/B tests** on targeted retention campaigns
- Collect additional features: billing history, tenure, contract type

---

## Repository Structure

```plaintext
 SyriaTel-Customer-Churn/
│
├── 📁 data/
│   └── syria_tel_churn.csv
├── 📁 images/
│   ├── churn_distribution.png
│   ├── churn_by_state_top20.png
│   ├── heatmap_correlations.png
│   ├── conf_matrix_all_models.png
│   ├── roc_curves_all_models.png
│   └── model_scores_comparison.png
├── 📁 notebooks/
│   └── final_modeling.ipynb
├── 📄 README.md
├── 📄 requirements.txt
└── 📄 .gitignore

## How to Run

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Tinah-91/SyriaTel-Customer-Churn-.git
   cd SyriaTel-Customer-Churn

2. Install dependencies:
    ```
    pip install -r requirements.txt

3. Run the notebook:

 ```
    jupyter notebook SyriaTel Customer Churn.ipynb

# License

This project is licensed under the MIT License



