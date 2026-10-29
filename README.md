
# Customer Churn Prediction

## Project Overview
This capstone project analyses customer churn for AlphaCom, a telecommunications provider. The goal is to understand customer characteristics associated with churn and develop classification models that can help the business identify customers who may be at risk of leaving.

## Business Objective
Build and evaluate churn-prediction models and identify patterns that can support a more proactive, data-informed customer-retention strategy.

## Dataset
The project report describes a dataset containing **12,055 customer records and 20 variables** covering:
- Customer demographics
- Tenure and subscribed services
- Contract and billing details
- Monthly and total charges
- Churn status (target variable)

The data includes customer-level fields such as `tenure`, `InternetService`, `Contract`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`, and `Churn`.

> The dataset itself is not included in this repository. Add it only if you have permission to share it and it contains no sensitive or identifying information.

## Tools and Techniques
- Python
- Pandas and NumPy for data preparation and analysis
- Exploratory Data Analysis (EDA) and visualisation
- Data cleaning, category standardisation, missing-value treatment, and logical consistency checks
- Scikit-learn classification models
- SMOTE to address class imbalance in training data
- Feature scaling and feature selection for Logistic Regression
- Hyperparameter tuning
- Model evaluation using accuracy, precision, recall, F1-score, ROC-AUC, and confusion matrix

Only retain tools and techniques here that are present in your notebook and that you can explain in an interview.

## Workflow
1. Define the churn problem and review the dataset.
2. Assess data quality, duplicates, missing values, inconsistent categories, and anomalous values.
3. Clean and standardise the data.
4. Explore churn patterns across customer, service, contract, and billing variables.
5. Prepare training and test data.
6. Train a Logistic Regression baseline and compare advanced models, including Decision Tree, Bagging, Random Forest, AdaBoost, Gradient Boosting, and XGBoost.
7. Tune selected models and evaluate their performance on the test set.
8. Translate the findings into customer-retention recommendations.

## Key Findings from the Final Report
- The report describes an observed churn rate of **28.2%** in the dataset.
- Month-to-month customers had a higher observed churn rate (**46.0%**) than one-year (**11.3%**) and two-year contract customers (**3.3%**).
- Customers who churned had a lower median tenure (about **11 months**) than customers who stayed (about **35 months**).
- Churn varied by internet service type; the report shows a higher observed churn rate among Fiber optic customers (**44.9%**) than DSL customers (**21.7%**).
- Electronic-check users were identified as a segment worth monitoring for retention.

These are associations in this dataset; they do not establish that a particular service or billing choice causes churn.

## Final Model and Trade-offs
The final report selected a **tuned AdaBoost model** because it achieved the highest recall for the churn class among the tuned models.

| Metric | Reported test result |
|---|---:|
| Recall | 97.75% |
| Precision | 34.87% |
| Accuracy | 50.06% |
| F1-score | 51.40% |
| ROC-AUC | 78.20% |

The confusion matrix reported 955 true positives, 22 false negatives, 855 true negatives, and 1,784 false positives.

**Interpretation:** The model identified most actual churners, but it also flagged many customers who did not churn. This may be useful when missing a potential churner is especially costly, but it could create unnecessary outreach and retention costs. The model should not be treated as production-ready without further validation, threshold/cost analysis, and monitoring.

## Business Recommendations
- Prioritise retention outreach for customers identified as high risk, while validating the model's alerts.
- Review the experience of month-to-month customers and consider appropriate retention offers.
- Improve onboarding and support for newer customers.
- Review the electronic-check payment experience and investigate related customer feedback.
- Monitor precision, recall, false-positive volume, and retention outcomes if the model is piloted.

## Repository Contents 
- `README.md`  project summary, workflow, findings, and limitations
- `customer_churn_prediction_report.pdf` final project report
- `customer_churn_prediction_notebook.html`  exported notebook for browser viewing, if included

## Limitations
- The results depend on the dataset and preprocessing decisions documented in the project report.
- High recall comes with low precision in the selected tuned AdaBoost model, so many predicted high-risk customers are false positives.
- The reported metrics should be rechecked by running the notebook and validating the evaluation setup before using the model for real business decisions.
- The dataset appears to be a project dataset; results should not be interpreted as evidence about all telecom customers.

## How to Review
Start with the notebook for the analysis and model-building workflow, then read the final report for the detailed business context, data-cleaning decisions, model comparison, results, and recommendations.

