# SyriaTel Customer Churn Prediction

Predicting which customers are likely to leave SyriaTel’s telecom services using machine learning.

**Author** by [Tinah Ngei](https://github.com/Tinah-91)

## Business Objective

SyriaTel wants to:

- Identify customers who are likely to churn.
- Understand why they churn.
- Implement proactive retention strategies.

 Predict churn  
 Understand drivers of churn  
 Recommend customer retention strategies

---

## Dataset Description

The dataset contains 3,333 customer records and 20+ features including:

| Feature                  | Description                                 |
|--------------------------|---------------------------------------------|
| `account length`         | Days a customer has been active             |
| `international plan`     | Whether they have an international plan     |
| `voice mail plan`        | Whether they have a voicemail plan          |
| `total day minutes`      | Minutes spent during the day                |
| `customer service calls` | Number of times customer called support     |
| `churn`                  | Target: Yes (churned) / No (not churned)    |

---

## Data Preprocessing

We:

- Cleaned and encoded categorical data.
- Handled multicollinearity.
- Scaled features for models like SVM and KNN.
- Performed a stratified 80/20 train-test split.

## Exploratory Data Analysis (EDA)

We examined:

- Churn distribution
- Categorical relationships (e.g., churn by plan type)
- Correlation heatmaps

**Key Visuals:**

- ![Churn by International Plan](images/churn_by_international_plan.png)
- ![Churn by Voicemail Plan](images/churn_by_voice_mail_plan.png)
- ![Top 20 State Distribution](images/top20_state_churn_distribution.png)
- ![Correlation Heatmap](images/correlation_heatmap.png)

---

## Machine Learning Models

We trained and evaluated five classifiers:

| Model                | Type               |
|----------------------|--------------------|
| Logistic Regression  | Linear             |
| Random Forest        | Ensemble (Bagging) |
| K-Nearest Neighbors  | Distance-based     |
| Support Vector Machine | Margin-based    |
| XGBoost              | Ensemble (Boosting)|

**Evaluation Metrics:**

- Accuracy
- Precision, Recall, F1-Score
- Confusion Matrix
- ROC Curve & AUC

---

## Model Evaluation Summary

| Model                | Accuracy | Precision | Recall | F1 Score | AUC  |
|----------------------|----------|-----------|--------|----------|------|
| Logistic Regression  | 87%      | 75%       | 60%    | 66%      | 0.86 |
| KNN                  | 85%      | 71%       | 58%    | 64%      | 0.82 |
| Random Forest        | 90%      | 83%       | 67%    | 74%      | 0.91 |
| SVM                  | 86%      | 74%       | 62%    | 67%      | 0.85 |
| XGBoost              | **91%**  | **85%**   | **69%**| **76%**  | **0.93** ✅ Best Model

**ROC Curve:**
![ROC Curves](images/model_roc_comparison.png)

---

## Business Recommendations

Based on insights and feature importance:

- Customers with **many support calls** → **Improve customer experience**
- Customers with **international plans** → **Review pricing, usability**
- Customers without **voice mail plans** → **Upsell bundled services**
- Target customers by **state** → **Run regional campaigns**

---

## Conclusion

- Built and evaluated 5 ML models.
- XGBoost gave the best performance (91% accuracy, 0.93 AUC).
- Identified key churn drivers to reduce loss.

---

## Repository Structure

├── images/
│   ├── churn_by_international_plan.png
│   ├── churn_by_voice_mail_plan.png
│   ├── correlation_heatmap.png
│   ├── top20_state_churn_distribution.png
│   ├── model_roc_comparison.png
│   └── feature_importance_xgboost.png
├── data/
│   └── churn_clean.csv
├── notebooks/
│   └── SyriaTel_Churn_Analysis.ipynb
├── README.md
└── requirements.txt

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



