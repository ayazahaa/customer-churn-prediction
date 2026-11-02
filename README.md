# Customer Churn Prediction

Can we predict which telecom customers are likely to leave?

I built this project using the **IBM Telco Customer Churn** dataset to explore customer behavior and train machine learning models to predict churn.

The main goal was to identify customers who might leave while balancing the number of customers correctly identified against false alarms.

## Results

Here are the results from my final model:

| Metric | Score |
|---|---:|
| ROC-AUC | **0.848** |
| Average Precision | **0.663** |
| Recall | **78.3%** |
| Precision | **54.0%** |
| F1-score | **0.639** |
| Accuracy | **76.5%** |

The model correctly identified **293 out of 374 customers who left**. It missed 81 customers and incorrectly flagged 250 who stayed.

This helped me understand why accuracy alone isn't enough when working with imbalanced data.

*Note: I had explored the test split earlier in the project, so these results aren't a completely independent evaluation. Testing on new data would give a more reliable estimate of performance.*

## What I discovered

I explored 7,043 customer records and found some interesting patterns:

- Customers with month-to-month contracts had a much higher churn rate (42.7%) compared to two-year contracts (2.8%).
- Customers using electronic checks had a 45.3% churn rate.
- Fiber-optic customers had a 41.9% churn rate.
- Customers who left generally had shorter tenure and higher monthly charges.

These patterns helped me understand which features might be useful for predicting churn.

## How I built the project

1. **Data Cleaning:** Checked missing values, duplicates, and data types.
2. **Exploratory Data Analysis:** Studied customer behavior and its relationship with churn.
3. **Preprocessing:** Encoded categorical features, standardized numerical features, and split the data.
4. **Model Training:** Compared Logistic Regression, Balanced Logistic Regression, Decision Tree, Random Forest, and XGBoost.
5. **Model Improvement:** Used cross-validation, hyperparameter tuning, and threshold optimization.
6. **Evaluation:** Compared models using precision, recall, F1-score, ROC-AUC, and average precision.
7. **Feature Importance:** Investigated which features contributed most to model performance.

## Visualizations

### Threshold Selection

![Threshold Selection](assets/threshold_selection.png)

### Model Evaluation

![Model Evaluation](assets/model_evaluation.png)

### Feature Importance

![Feature Importance](assets/feature_importance.png)

Contract type and tenure turned out to be the most important features in the final permutation-importance analysis.

## Tools Used

Python