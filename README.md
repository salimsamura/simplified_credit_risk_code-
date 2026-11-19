# Simplified Credit Risk Model

## Project Overview

This project is a simplified version of my original **Credit Risk Modeling and Analysis** project, which explored credit risk assessment using historical LendingClub loan data.

The original project involved developing a comprehensive credit risk framework using three key components:

- **Probability of Default (PD):** Estimates the likelihood that a borrower will default on a loan.
- **Loss Given Default (LGD):** Estimates the proportion of exposure that may be lost if a borrower defaults.
- **Exposure at Default (EAD):** Estimates the amount outstanding when a default occurs.

After working on the original framework, I developed this simplified model to focus specifically on predicting borrower default risk using a smaller, more practical set of features.

## Origin of the Simplified Model

The simplified model originated from my larger Credit Risk Modeling project.

During the development of the original model, I worked with extensive historical loan data, performed exploratory data analysis, engineered features, and developed predictive models to estimate credit risk.

However, the original modeling framework involved numerous variables and complex preprocessing steps.

I wanted to explore whether a smaller set of readily available borrower and loan characteristics could still provide useful predictions of default risk.

This led to the development of the **Simplified Credit Risk Model**.

Rather than replacing the original project, this model serves as a separate experiment focused on reducing feature complexity while maintaining a practical approach to credit risk assessment.

## Dataset

The project uses historical LendingClub loan data derived from the dataset used in my original credit risk analysis.

The simplified dataset focuses on the following variables:

| Feature | Description |
|---|---|
| Funded Amount | Amount funded for the loan |
| Loan Term | Repayment duration |
| Annual Income | Borrower's reported annual income |
| Employment Length | Length of employment |
| Home Ownership | Borrower's housing status |
| Loan Purpose | Reason for obtaining the loan |
| Address State | Borrower's state of residence |

Historical loan status was used to construct the target variable.

- **0 — Non-default:** Fully Paid
- **1 — Default:** Charged Off or Default

The simplified modeling dataset contained approximately 228,046 observations.

## Methodology

### 1. Data Preprocessing

The preprocessing workflow involved selecting relevant variables, defining the target variable, handling categorical features, and preparing the dataset for machine learning.

Categorical variables such as home ownership, loan purpose, and address state were converted into numerical representations using one-hot encoding.

### 2. Train-Test Split

The dataset was divided into training and testing sets using an 80/20 split.

Stratified sampling was applied to preserve the distribution of default and non-default observations.

### 3. Model Development

An **XGBoost Classifier** was developed to predict the probability of borrower default.

XGBoost was selected because of its ability to model nonlinear relationships and interactions between borrower characteristics.

### 4. Model Validation

Model evaluation included:

- Stratified five-fold cross-validation
- Classification accuracy
- ROC curve analysis
- Predicted default probabilities
- Feature importance analysis

The cross-validation accuracy was approximately **81%**.

However, accuracy alone is not sufficient to establish model quality, particularly when the target classes are imbalanced. Additional measures such as ROC-AUC, precision, recall, and calibration are important for assessing practical performance.

## Credit Risk Decision Framework

The model generates a predicted probability of default for each borrower.

These probabilities can be used to explore different hypothetical lending decision thresholds.

For example, borrowers with lower estimated default probabilities may be categorized as lower-risk applicants.

The project also explores how changing probability thresholds affects the proportion of applications approved and the observed default rate among approved borrowers.

These decisions are for educational analysis and do not represent a validated production lending policy.

## Relationship to the Original Project

The two projects have different objectives.

**Original Credit Risk Modeling Project**

- Comprehensive credit risk analysis
- PD, LGD, and EAD modeling
- Expected credit loss estimation
- Extensive feature engineering
- Broader portfolio risk assessment

**Simplified Credit Risk Model**

- Focuses specifically on probability of default
- Uses fewer borrower and loan characteristics
- Implements XGBoost classification
- Evaluates predicted default probabilities
- Explores simplified lending decision thresholds

The simplified model is an extension of the original project's ideas rather than an entirely unrelated analysis.

## Limitations

The model was developed using historical LendingClub data for educational and portfolio purposes.

Its predictions should not be interpreted as production-ready credit decisions without further validation.

Important considerations include class imbalance, probability calibration, potential data leakage, fairness testing, changing economic conditions, and the representativeness of the historical dataset.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- JupyterLab

## Project Purpose

This project demonstrates my ability to simplify a larger analytical problem, prepare structured financial data, develop a machine learning classification model, evaluate predictive performance, and interpret model outputs in a credit risk context.

It also reflects my continued development in financial analytics, credit risk modeling, and applied machine learning.

**Focus:** Data Analytics | Credit Risk Modeling | Machine Learning
