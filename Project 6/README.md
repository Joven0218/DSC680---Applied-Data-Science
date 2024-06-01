Commercial Insurance Churn Prediction

Introduction

Customer retention is crucial for the long-term success of commercial insurance businesses. This project aims to tackle the issue of customer churn by leveraging a comprehensive dataset of business policies. By developing a predictive model, we aim to help insurance companies identify potential cancellations, enhance retention rates, and drive profitability.
Problem Statement

High customer churn rates in the commercial insurance industry lead to revenue loss and hinder lasting client relationships. This project seeks to develop a machine learning model to accurately predict the likelihood of policy cancellations based on various features in the dataset.
Data Source

The dataset includes:

    Policy label, effective date, expiration date, cancellation date
    Product code, subline code
    Address details (street, city, county, zip, state)
    Written premium amount, total loss payments, total reserve

Summary of Milestones 1-3
Target Variable

    Cancellation Indicator: Binary variable derived from the cancellation date column (1 for cancellations, 0 otherwise).

Data Preparation

    Cleaning and preprocessing: Handling missing values and removing duplicates.
    Encoding categorical variables.
    Creating new features: Policy duration, time to cancellation, claim frequency, and loss ratio.

Exploratory Data Analysis (EDA)

    Identified patterns such as geographical clusters of cancellations and seasonal variations.
    Data span: 69,567 policies over three years with 4,656 cancellations (7% cancellation rate).

Key Insights

    High cancellation rates in Florida and Louisiana.
    Product codes MBOP and BBOP showed the highest potential for investigation.
    Significant financial impact with $5 million in premium lost due to cancellations.

Modeling
Initial Linear Regression Model

    Performance:
        Training R2: 0.128
        Test R2: 0.049
        High RMSE and MAE values indicating poor fit and high prediction error.

Decision Tree Model

    Initial Model:
        Training R2: 0.999 (overfitting)
        Test R2: -0.052 (poor generalization)
    Tuned Model:
        Best Hyperparameters: {'max_depth': 5, 'min_samples_leaf': 4, 'min_samples_split': 2}
        Improved performance with Test R2: 0.47

Random Forest Model

    Initial Model:
        Training R2: 0.919
        Test R2: 0.418 (overfitting)
    Tuned Model:
        Best Hyperparameters: {'max_depth': 5, 'min_samples_leaf': 4, 'min_samples_split': 2, 'n_estimators': 300}
        Best Test R2: 0.478, RMSE: 77.19, MAE: 57.37

Conclusion

The tuned Random Forest model showed the best performance, explaining 48% of the variance in the target variable with relatively small prediction errors. Further improvements could be achieved by incorporating additional features like customer demographics, payment history, and textual analysis of cancellation reasons.
Future Work

    Include customer demographics (age, gender, location, income level).
    Analyze customer payment behaviors (frequency, punctuality, method).
    Conduct textual analysis on cancellation reasons for deeper insights.

By continuously refining the model, we aim to make more informed decisions and take proactive measures to mitigate cancellations.
