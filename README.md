# Credit_Risk_Analysis

Evaluating Credit Risk using resampling models

## Overview of the Loan Prediction Analysis

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. 

This project employs different techniques to train and evaluate models with unbalanced classes. The ***"imbalanced-learn"*** and ***"scikit-learn"*** libraries will be used to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, the data will be oversampled using the ***"RandomOverSampler"*** and ***"SMOTE"*** algorithms, and undersampled using the ***"ClusterCentroids"*** algorithm. A combination approach of over- and undersampling using the ***"SMOTEENN"*** algorithm will also be used.

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
 


## Summary

In the first four models undersampled, oversampled and did a combination of both to try and determine which model is best at predicting which loans are the highest risk. 
The next two models resampled the data using ensemble classifiers to try and predict which which loans are high or low risk. 
In the first four models, the accuracy score is not as high as the ensemble classifiers and the recall in the oversampling/undersampling/mixed models is low as well. 

Typically in these models, a good result is when there is a good balance of recall and precision. Hence, the ensemble classifiers are better than the first four models.
It appears that the Easy Ensemble had the best balance of all the models because of it's high accuracy score and good balance of precision and recall scores.

