# Credit Analysis Report

## Overview of the Analysis

The purpose of this analysis is to determine if loans are healthy or have a high-risk of default. A successful model will accurately identify high-risk loans and allow banks to prevent defaults through early identification. 

* Data from 77536 loans were used to create `LogisiticRegression` model. Each row contained the following information:
  * `loan_size` (in dollars)
  * `interest_rate` (as a percentage)
  * `borrower_income` (in dollars)
  * `debt_to_income` (as a ratio)
  * `num_of_accounts`
  * `derogatory_marks` (ranged from 0 to 4)
  * `total_debt` (in dollars)
  * `loan_status` was our target variable where a 0 indicated a healthy loan and a 1 indciated a high-risk loan.

* We split the data into a training set and a test set using `train_test_split` from `Scikit-Learn`
  * The training set contained 58152 data points
  * The test set contained 19384 data points
* Once the data was split, we fit the model using the training data
* Finally, we used the test data to determine the model's accuracy, which can be seen below

## Results

Confusion Matrix
[18663   102]
[   56   563]

* Balanced accuracy score: 0.952

* Healthy Loans
  * Precision: 1.00
  * Recall: 0.99
  * Accuracy: 1.00

* High-Rist Loans
  * Precision: 0.85
  * Recall: 0.91
  * Accuracy: 0.88

## Summary

The model is very good at predicting healthy loans, as shown by the f1-score of 1.

It is much worse however, at predicting high-risk loans, with an f1 score of only .88. 

Because the objective of this model is to identify high-risk loans, we should consider ways to tweak the model for better accuracy of high-risk loans. Some potential options would be to resample the data or scale the input features.
