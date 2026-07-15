# Customer Churn Prediction

## Project Overview

This project develops machine learning models to predict customer churn using customer demographics, engagement behaviour and account activity data.

The objective is to identify customers at risk of leaving the company and support proactive customer retention strategies through predictive analytics.

The project follows a complete end-to-end machine learning workflow, including:

- Data Understanding
- Exploratory Data Analysis (EDA)
- Data Preprocessing
- Model Development
- Model Evaluation
- Model Comparison
- Business Recommendations

---

## Business Problem

Customer acquisition is significantly more expensive than customer retention.

Identifying customers likely to churn allows businesses to intervene early, improve customer satisfaction and reduce revenue loss.

The goal of this project is to build an early warning system capable of identifying customers at high risk of churn before they leave the company.

---

## Dataset

- **Dataset Size:** 440,833 observations
- **Predictor Variables:** 11 features
- **Target Variable:** `Churn`

### Features

- Age
- Gender
- Tenure
- Usage Frequency
- Support Calls
- Payment Delay
- Subscription Type
- Contract Length
- Total Spend
- Last Interaction
- Churn (Target Variable)

---

## Project Structure

```text
customer-churn-prediction/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_preprocessing.ipynb
│   ├── 04_logistic_regression.ipynb
│   ├── 05_random_forest.ipynb
│   ├── 06_xgboost.ipynb
│   ├── 07_model_comparison.ipynb
│   └── 08_business_recommendations.ipynb
│
├── requirements.txt
│
└── README.md
```

---

## Exploratory Data Analysis

Several important patterns emerged during exploratory analysis:

- Customers on **monthly contracts** exhibited substantially higher churn rates.
- **Support Calls** emerged as one of the strongest indicators of churn.
- Customers with increasing **payment delays** were significantly more likely to leave.
- Customers with lower **total spend** exhibited higher churn probabilities.
- Reduced customer engagement was associated with increased churn risk.

### One Limitation

Correlation analysis measures only **linear relationships** and may fail to capture important non-linear behaviour.

For example:

```text
0 support calls  → 30% churn
5 support calls  → 95% churn
10 support calls → 100% churn
```

Although this relationship is extremely important, a simple correlation coefficient may underestimate its strength.

---

## Data Preprocessing

The preprocessing pipeline included:

- Removal of non-predictive identifiers (`CustomerID`)
- Handling missing target values
- One-hot encoding of categorical variables
- Prevention of the dummy variable trap
- Stratified train-test splitting
- Feature standardisation using `StandardScaler`
- Prevention of data leakage during scaling

---

## Models Developed

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.89 | 0.92 | 0.89 | 0.904 | 0.96 |
| Random Forest | 0.9995 | 0.9999 | 0.9992 | 0.9996 | 0.999999 |
| XGBoost | 0.9999 | 1.0000 | 0.9999 | 0.9999 | 0.999999 |

---

## Model Comparison

### Logistic Regression
- Most interpretable model.
- Coefficients provided clear explanations of churn drivers.
- Served as a strong baseline model.

### Random Forest
- Captured complex non-linear relationships.
- Significantly improved predictive performance.

### XGBoost
- Achieved the strongest overall predictive performance.
- Produced the highest accuracy, recall and ROC-AUC scores.

---

## Feature Importance

The most influential predictors of customer churn were:

1. Contract Length (Monthly)
2. Support Calls
3. Total Spend
4. Payment Delay
5. Last Interaction
6. Age

These findings were highly consistent across Logistic Regression, Random Forest and XGBoost models.

---

## Key Business Insights

- Customers on monthly contracts were significantly more likely to churn.
- Frequent support calls strongly indicated customer dissatisfaction.
- Payment delays acted as an early warning signal for churn.
- Lower customer spending was associated with increased churn risk.
- Customer engagement and interaction frequency played an important role in retention.

---

## Business Recommendations

Based on the analysis, the following recommendations were proposed:

- Target customers on monthly contracts with retention campaigns.
- Prioritise customers with increasing support call volumes.
- Monitor payment delays as an early indicator of churn risk.
- Improve customer engagement initiatives.
- Deploy the XGBoost model as an automated churn monitoring system.
- Refer high-risk customers to customer retention teams for intervention.

---

## Deployment Recommendation

XGBoost achieved the strongest predictive performance and would be the preferred deployment model.

In a production environment, the model could be used as an automated early warning system that continuously monitors customer behaviour and flags customers with a high probability of churn for proactive intervention.

---

## Limitations

The near-perfect performance achieved by Random Forest and XGBoost is unusual for real-world churn datasets and warrants further investigation for potential data leakage or target leakage.

Additional validation using future customer data or external datasets would be required before deployment into production environments.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- XGBoost
- Jupyter Notebook

---

## Installation

Clone the repository:

```bash
git clone <repository-url>
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Repository Description

> End-to-end customer churn prediction project using Logistic Regression, Random Forest and XGBoost with business recommendations for customer retention.

---

## Repository Topics

```text
machine-learning
data-science
customer-churn
classification
xgboost
random-forest
logistic-regression
predictive-analytics
python
```

---

## Summary

> I developed an end-to-end customer churn prediction pipeline covering exploratory data analysis, preprocessing, model development, model comparison and business recommendations. Logistic Regression provided the highest interpretability, while XGBoost achieved the strongest predictive performance. The project highlighted the trade-off between explainability and performance and concluded with actionable strategies for reducing customer churn and improving customer retention.

---

## Author

**Nkosikhona Khoza**

BSc Mathematics, Statistics and Data Science  
University of Cape Town
