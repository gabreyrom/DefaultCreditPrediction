# Default Credit Prediction

Exploratory data analysis and machine learning models to predict whether a credit card client will default on their next payment, based on the [UCI "Default of Credit Card Clients"](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients) dataset.

## Overview

This project walks through a full data science workflow on the dataset:

1. **Exploratory Data Analysis (EDA)** — distributions of payment delays, bill amounts, monthly payments, and credit limits; default rate breakdown by gender, marriage status, and age group.
2. **Feature Engineering** — categorical encoding (sex, marriage, age brackets, credit limit brackets), log transforms for skewed monetary variables, relative payment/bill ratios, and rolling statistics (mean/std) of payment delays.
3. **Preprocessing** — feature selection with `SelectKBest` (ANOVA F-test) and Min-Max scaling, wrapped in an `sklearn` `Pipeline`.
4. **Modeling** — several classifiers are trained and evaluated with 10-fold cross-validation:
   - Naive Bayes
   - Random Forest
   - Gradient Boosting
   - AdaBoost
   - Bagging Classifier
   - K-Nearest Neighbors
5. **Evaluation** — accuracy, ROC curves, AUC, and confusion matrices for each model.

## Dataset

`default.xls` contains 30,000 records of credit card clients in Taiwan, with features such as:

- Demographic info: sex, education, marriage status, age
- Credit limit (`LIMIT_BAL`)
- Repayment status for the past 6 months (`PAY_1`–`PAY_6`)
- Bill statement amounts for the past 6 months (`BILL_AMT1`–`BILL_AMT6`)
- Previous payment amounts for the past 6 months (`PAY_AMT1`–`PAY_AMT6`)
- Target: whether the client defaulted on the next month's payment

## Repository contents

| File | Description |
|---|---|
| `Default_clean.ipynb` | Main Jupyter notebook with the full EDA, feature engineering, and modeling pipeline |
| `default.xls` | Raw dataset (UCI Default of Credit Card Clients) |
| `Proyect 2 - Credit Cards Default Payments.pptx` | Project summary presentation |

## Getting started

### Requirements

- Python 3
- Jupyter Notebook / JupyterLab
- `pandas`, `numpy`, `matplotlib`, `scikit-learn`, `patsy`, `xlrd`

Install dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn patsy xlrd
```

### Running

```bash
jupyter notebook Default_clean.ipynb
```

Run the cells in order — the dataset (`default.xls`) is loaded from the repository root.
