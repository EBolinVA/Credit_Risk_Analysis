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

### Oversampling
1. Naive Random Oversampling

    * Balanced Accuracy Score: 0.655

    * Precision:    - 0.01 for predicting high-risk
                    - 1.00 for predicting low-risk

    * Recall: 70% at catching true high-risk, and 61% at identifying true low-risk. 

![image of randomoversampling_scores](https://github.com/EBolinVA/Credit_Risk_Analysis/blob/main/Starter_Code/Images/RandomOversampling_scores.png)
 
2. SMOTE (Synthetic Minority Oversampling TEchnique)

    * Balanced Accuracy Score: 0.662

    * Precision:    -0.01 for predicting high-risk
                    -1.00 for predicting low-risk
    
    * Recall: 63% at catching true high-risk, and 69% at identifying true low-risk

![image of SMOTE_oversampling_scores](https://github.com/EBolinVA/Credit_Risk_Analysis/blob/main/Starter_Code/Images/SMOTE_oversampling_scores.png)

### Undersampling
3. ClusterCentroids

    * Balanced Accuracy Score: 0.545

    * Precision:    -0.01 for predicting high-risk
                    -1.00 for predicting low-risk
    
    * Recall: 69% at catching true high-risk, and 40% at catching true low-risk.

![image of ClusterCentroids_scores](https://github.com/EBolinVA/Credit_Risk_Analysis/blob/main/Starter_Code/Images/ClusterCentroides_undersampling_scores.png)


### Combination of Over- and Undersampling
4. SMOTEENN (SMOTE with Edited Nearest Neighbor)

    * Balanced Accuracy Score: 0.642

    * Precision:    -0.01 for predicting high-risk
                    -1.00 for predicting low-risk
    
    * Recall: 70% at catching true high-risk, and 58% at catching true low-risk.

![image of SMOTEENN_scores](https://github.com/EBolinVA/Credit_Risk_Analysis/blob/main/Starter_Code/Images/SMOTEENN_oversampling_scores.png)

### Ensemble Classifiers
5. Balanced Random Forest Classifier

    * Balanced Accuracy Score: 0.789

    * Precision:    -0.03 for predicting high-risk
                    -1.00 for predicting low-risk
    
    * Recall: 70% at catching true high-risk, and 87% at catching true low-risk.

![image of BRFC_scores](https://github.com/EBolinVA/Credit_Risk_Analysis/blob/main/Starter_Code/Images/BRFC_ensemble_scores.png)

6. Easy Ensemble AdaBoost Classifier

    * Balanced Accuracy Score: 0.932

    * Precision:    -0.09 for predicting high-risk
                    -1.00 for prediciting low-risk
    
    * Recall: 92% at catching true high-risk, and 94% at identifying true low-risk.

![image of EasyEnsemble_AdaBoost_scores](https://github.com/EBolinVA/Credit_Risk_Analysis/blob/main/Starter_Code/Images/EasyEnsemble_AdaBoost_scores.png)


## Summary
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.

#### None of the Oversampling methods are desirable in predicting credit risk
  * The Naive Random Oversampling model over-predicted high-risk loans. While the sensitivity is 70% for predicting high-risk, there were many "actually low-risk" caught up in the group as "predicted high-risk".

  * Likewise, the SMOTE method was better at predicting low-risk, and the sensitivities for low- and high-risk were 63% and 69% respectively.

#### The Undersampling method did not perform well at predicting credit risk
  * Using the ClusterCentroids model, the balanced accuracy score was lower than any of the oversampling methods at 55%. The recall for predicting low-risk was significantly lower at 40%. 

#### Using a combination of Over- and Undersampling did not improve results
  * SMOTEENN performed no better than our first model, Naive Random Sampling. Both had similar scores, with the balanced accuracy score for SMOTEENN at 64%. Recall for low-risk was 58% and high-risk was 70%.

#### Ensemble Classifiers proved most accurate at predicting credit risk
  * The Balanced Random Forest Classifier model had a balanced accuracy score of 79%, higher than the previous models listed. It is slightly better at predicting high-risk at 3% with recall of 70%. 

  * The EasyEnsemble with AdaBoost wins out for predicting credit risk on this dataset. AdaBoost is an ensemble learning method (also known as “meta-learning”) which was initially created to increase the efficiency of binary classifiers. AdaBoost uses an iterative approach to learn from the mistakes of weak classifiers, and turn them into strong ones. With a balanced accuracy score of 93% and similar recall scores for both high- and low-risk, I would recommend employing this model for future credit risk applications. 

