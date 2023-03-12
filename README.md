# Credit_Risk_Analysis


## Overview
This project's objective is to evaluate the performance of several machine learning models on the ability to predict credit risk.

Credit risk data files provide inherently unbalanced classification- in our credit card dataset from LendingClub, the target variable "loan_status" contains 68,470 low-risk records, and only 347 high-risk records. I am comparing and evaluating the following algorithms on this data to predict risk:

    - RandomOverSampler
    - SMOTE
    - ClusterCentroids
    - SMOTEENN
    - BalancedRandomForestClassifier
    - EasyEnsembleClassifier

## Results

Descriptions of the balanced accuracy scores and the precision and recall scores of all six machine learning models:

1. Naive Random Oversampling

  ``from imblearn.over_sampling import RandomOverSampler``

    - Balanced Accuracy Score: 0.655

    - Precision: 0.01 for predicting high-risk, 1.00 for predicting low-risk

    - Recall: 



Summary: Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.