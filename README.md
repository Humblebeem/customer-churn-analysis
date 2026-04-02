# customer-churn-analysis

Customer churn prediction using the Telco Customer Churn dataset (Logistic Regression, Random Forest, Gradient Boosting).
Project Overview
This project builds a machine learning pipeline to predict customer churn for a telecom company. The goal is to identify customers who are likely to leave so the business can proactively target them with retention offers.
Dataset
The project uses the Telco Customer Churn dataset, which includes:

Customer demographics
Service information (phone, internet, add‑ons)
Contract type and payment method
Monthly and total charges
Target variable: Churn (Yes/No)

Methodology


Data Cleaning

Converted TotalCharges from string to numeric.
Removed rows with missing values in TotalCharges.
Dropped customerID since it is an identifier and not predictive.



Feature Engineering & Encoding

One‑hot encoded categorical variables using pandas.get_dummies(..., drop_first=True).
Defined Churn_Yes as the target variable and used all other columns as features.



Modeling

Split data into training and test sets (80/20) with stratification on the target.
Trained multiple models:

Logistic Regression (baseline)
Random Forest Classifier
Gradient Boosting Classifier


Also experimented with:

Class‑weighted Logistic Regression to handle class imbalance.
Adjusting the decision threshold (e.g., 0.4 instead of 0.5) to improve recall for churners.





Evaluation

Metrics used:

Accuracy
Precision, Recall, F1‑score
Confusion Matrix
ROC‑AUC


Baseline Logistic Regression achieved around 0.80 accuracy, with reasonable recall for churn.
Class weighting and threshold tuning improved churn recall at the cost of some precision on non‑churn customers.



Key Insights
Feature importance analysis suggests:

Higher MonthlyCharges and TotalCharges are associated with higher churn risk.
Customers with shorter tenure are more likely to leave.
Fiber optic internet service users churn more often than DSL users.
Electronic check payment method and paperless billing are linked to higher churn.
Long‑term two‑year contracts significantly reduce churn likelihood.

Files

customer_churn_analysis.ipynb – Main notebook with data exploration, modeling, and evaluation.

How to Run

Clone the repository:

git clone https://github.com/Humblebeem/customer-churn-analysis.git


Open the notebook in Jupyter or Google Colab.
Install required Python packages (for example):

pandas
numpy
scikit-learn
matplotlib
seaborn


Run the cells in order.

Possible Next Steps

Try more advanced models (e.g., XGBoost, LightGBM).
Perform more extensive hyperparameter tuning.
Use cost‑sensitive evaluation (different costs for missing a churner vs false alarms).
Deploy the model as an API or simple web app for business users.


Feel free to fork this repo, experiment with different models, and suggest improvements via issues or pull requests.
