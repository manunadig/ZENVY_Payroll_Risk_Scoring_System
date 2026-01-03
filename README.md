## ZENVY Payroll Risk Scoring System

## Project Overview

Payroll systems are vulnerable to errors and fraudulent activities due to irregular attendance, excessive overtime, and abnormal salary changes. This project implements a Payroll Risk Scoring System using data analysis and machine learning to automatically identify high-risk payroll records.

## Objectives

* Detect high-risk payroll records
* Engineer risk-based features from raw payroll data
* Compare three machine learning models
* Justify the best-performing model using mathematical reasoning
* Provide feature importance analysis** for explainability

## Dataset Description

The dataset is synthetically generated to simulate real-world payroll scenarios.

### Columns

| Column Name    | Description                                 |
| -------------- | ------------------------------------------- |
| emp_id         | Employee ID                                 |
| days_present   | Days present in the month                   |
| days_absent    | Days absent                                 |
| leaves_taken   | Paid leaves                                 |
| salary_prev    | Previous month salary                       |
| salary_curr    | Current month salary                        |
| overtime_hours | Overtime hours                              |
| risk_label     | Target variable (1 = High Risk, 0 = Normal) |

**Dataset Size:**

* Rows: 1000
* Columns: 8

---

## Risk Label Logic

A payroll record is labeled High Risk (1) if any of the following conditions occur:

* Low attendance (`days_present < 20`)
* Excessive overtime (`overtime_hours > 45`)
* Abnormal salary increase (`salary_curr - salary_prev > 12,000`)

Otherwise, the record is labeled **Normal (0)**.

## Feature Engineering

Additional features are derived to improve model performance:

* Attendance rate
* Salary change amount
* Salary change percentage
* Overtime-based risk indicators

## Exploratory Data Analysis (EDA)

* Payroll risk distribution
* Salary anomalies vs risk
* Correlation heatmap between features

EDA helps uncover patterns and validate assumptions before modeling.

## Machine Learning Models Used

Three models are trained and evaluated:

1. **Logistic Regression**

   * Linear probabilistic classifier using sigmoid function

2. **Random Forest Classifier**

   * Ensemble of decision trees reducing variance and capturing non-linearity

3. **Support Vector Machine (SVM)**

   * Margin-maximizing classifier with strong theoretical guarantees

## Model Evaluation Metrics

Each model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score

A comparison table is generated to identify the best-performing model.

## Final Model Selection

**Random Forest** is selected as the final model because:

* Payroll risk patterns are **non-linear**
* Features interact in complex ways
* Ensemble averaging minimizes generalization error

### Mathematical Justification

[
f(x) = \frac{1}{N} \sum_{i=1}^{N} f_i(x)
]
Where each (f_i) is a decision tree trained on a bootstrapped sample.

## Feature Importance Analysis

Random Forest feature importance highlights key risk drivers such as:

* Salary change
* Attendance rate
* Overtime hours

This improves transparency and trust in predictions.

## Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* Jupyter Notebook

## Author

**Manohar SN**
Python | Data Analysis | Machine Learning

