# Credit_Risk_Analysis

Evaluating credit risk using resampling models

## Overview of the Loan Prediction Analysis

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. 

This project employs different techniques to train and evaluate models with unbalanced classes. The ***"imbalanced-learn"*** and ***"scikit-learn"*** libraries will be used to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, the data will be oversampled using the ***"RandomOverSampler"*** and ***"SMOTE"*** algorithms, and undersampled using the ***"ClusterCentroids"*** algorithm. A combination approach of oversampling and undersampling using the ***"SMOTEENN"*** algorithm will also be used.

For comparison, two new machine learning models that reduce bias, ***"BalancedRandomForestClassifier"*** and ***"EasyEnsembleClassifier"***, will be used to predict credit risk. 



## Results of the Analysis

### **Naive Random Oversampling:**

- Balanced Accuracy Score: 0.67
- The high_risk precision is .01, recall score of 0.67 and an F1 score of 0.02
- The high number of the low_risk population yields a precision of 0.99 with a sensitivity of 0.67 and an F1 score of 0.80

<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130167999-cf551ceb-dabf-4904-8773-87561ed5a78c.png"
</p>

  
  
### **SMOTE Oversampling:**
  
- Balanced Accuracy Score: 0.63
- The high_risk precision is .01, recall score of 0.57 and an F1 score of 0.02
- The high number of the low_risk population yields a precision of 1.0 with a sensitivity of 0.68 and an F1 score of 0.81
  
<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130170081-10fc30c0-84eb-4de8-8b62-9abc61844527.png"
</p>
  

  
  
### **Cluster Centroids Undersampling:**
  
- Balanced Accuracy Score: 0.63
- The high_risk precision is .01, recall score of 0.57 and an F1 score of 0.02
- The high number of the low_risk population yields a precision of 1.0 with a sensitivity of 0.68 and an F1 score of 0.81
  
<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130170434-fda441d1-a442-4bda-b263-31559acb5448.png"
</p>


  

 ### **SMOTEENN - Combination Sampling to assess Credit Risk:**
  
- Balanced Accuracy Score: 0.65
- The high_risk precision is .01, recall score of 0.72 and an F1 score of 0.02
- The high number of the low_risk population yields a precision of 1.0 with a sensitivity of 0.58 and an F1 score of 0.73
  
<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130229510-927db442-5a18-4e4c-a2a9-2e15f64d69bd.png"
</p>
 


##
## Using Ensemble Algorithms to assess Credit Risk
###
### **Balanced Random Forest Classifier:**
  
- Balanced Accuracy Score: 0.79
- The high_risk precision is .03, recall score of 0.71 and an F1 score of 0.06
- The high number of the low_risk population yields a precision of 1.0 with a sensitivity of 0.88 and an F1 score of 0.93
  
<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130230711-17525845-ea02-4ae8-be02-901777acbcdd.png"
</p>  
  
- The following image extract shows the top 15 features in order of importance:
  
<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130231068-027ea979-2ead-4128-acd8-f629cb4c12f9.png"
</p>   

  
  
### **Easy Ensemble AdaBoost Classifier**

- Balanced Accuracy Score: 0.926
- The high_risk precision is .08, recall score of 0.91 and an F1 score of 0.14
- The high number of the low_risk population yields a precision of 1.0 with a sensitivity of 0.94 and an F1 score of 0.97
  
<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130232875-27f4ab41-d207-41f0-bc2f-cde9bed14ef2.png"
</p>  
  
 
  
## Summary

<p align="center">
<image src = "https://user-images.githubusercontent.com/82583576/130280886-97b3da82-92fb-48a4-a3cc-6336302020ad.png"
</p>  
  
  
  
  
- **Balanced Accuracy Score:**  
  
  This metric is used to evaluate how good a binary classifier is. It is not recommended when the classes are imbalanced (as is the case with the credit analysis). 
  In the first four models, using oversampling, undersampling and combination sampling, the balanced accuracy score are relatively the same and lower than the Ensemble Classifier  models.
  However, as the dataset inherently contains a much higher number of low risk loans, the accuracy score is not reliable in this case.
  
- **Precision:**
  
  The Precision score from all six models for the low-risk loans come to 1.00 – this quantifies the number of positive class predictions that actually belong to the positive class. This is the result of the low-risk loans making up a high percentage of all the loans in the samples.
  The precision score for the high-risk loans is relatively low for all six models - meaning the models potentially returns a high number of false positives for the high risk loans.
  
- **Recall (Sensitivity):**
  The recall score is an indication of how well the system returns predicted positive results, i.e. predicts low-risk when it is actually low risk and high-risk when it is actually high risk.
  The recall scores from all six models are over 50%. The Ensemble models have much higher recall scores than the oversampling or undersampling models.
  The high recall (sensitivity) scores is an indication that the predicted low-risk or high-risk are relatively reliable.
  
- **F1 Score:**
  The F1 score is a combination of precision and recall (sensitivity). A high F1 score is an indication that the predictions have low quantities of false positives and false negatives.
  All six models have a relatively high F1 score for the low risk loans (80% to 97%). However, the high risk loans have a much lower F1 score - potentially high number of false positives and false negatives. 
  
  
Typically in these models, a good result is when there is a good balance of recall and precision. Hence, the ensemble classifiers are better than the first four models.
The Easy Ensemble had the best balance of all the models because of it's high accuracy score and good balance of precision and recall scores.

