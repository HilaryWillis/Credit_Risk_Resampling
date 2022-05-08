# Module 12 Report Template

## Overview of the Analysis

The purpose of this challenge is to train and evaluate two different logistic regression models to determine which is stronger at correctly identifying the creditworthiness of borrowers. We, as analysts, received lending data on customers that included loan size, interest rate, borrower income, debt to income ratio, number of accounts, deragatory remarks, total debt and loan status. The loan status column indicates whether or not the loan is healthy (score of 0) or if the loan has a high risk of defaulting (score of 1). After reading the data, I prepared the data by counting the number of rows (customers) that had a healthy score of 0 and a high risk score of 1 to get the value counts. From there, the code split the data into two sets, a training dataset and a testing dataset which the model uses to make predictions (features) and to predict a target variable (variable).  Essentially, I supervised the model's learning by feeding it carefully selected data with known outcomes that the model can use to make the most accurate predictions that are possible. Initially, I used Logistic Regression model and assessed the models performance. This accuracy data led me to perform an Oversampling method on the dataset.


## Results

* Machine Learning Model 1:
    * Value Counts of Model 1: 0 = 75,036 / 1 = 2,500
    * Balanced Accuracy Score = .9520
    * Confusion Matrix: 
    
       [[18663   102]
       
        [   56   563]]
        
    * Classification Report: The results below show high precision of 1.00 for healthy loans, which is means out of all the times that the model predicted a testing data observation to be the value 0, 100% of   those predictions were correct. The precision for detecting fraudulent loans was .85, which means out of all the times that the model predicted a testing data observation to be the value of 1, 85% of those predictions were correct. Overall, this model has an accuracy score of 99%. Not bad, however I can see the dataset is imbalanced between the two classes.

                    precision    recall  f1-score   support

               0       1.00      0.99      1.00     18765
               1       0.85      0.91      0.88       619
               
          accuracy                          .99     19384
          macro avg     .92       .95       .94     19384
          weighted avg  .99       .99       .99     19384
    


* Machine Learning Model 2:
    * Value Counts of Model 2: 0 = 56,271 / 1 = 56,271
    * Balanced Accuracy Score = .9937
    * Confusion Matrix:
    
       [[18649   116]
    
        [    4   615]]
     
    * Classification Report: The results below show high precision of 1.00 for healthy loans, which is means out of all the times that the model predicted a testing data observation to be the value 0, 100% of   those predictions were correct. The precision for detecting fraudulent loans was .84, which means out of all the times that the model predicted a testing data observation to be the value of 1, 84% of those predictions were correct. Overall, this model has an accuracy score of 99%. This classification report for the oversampled class produced very similar results to the original set. 
    
                  precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.84      0.99      0.91       619
           
             
          accuracy                          .99     19834
          macro avg     .92       .99       .95     19834
          weighted avg  .99       .99       .99     19384
           

      
## Summary

It seems that the oversampled logistic regression machine learning module (model 2) worked very slightly better than the original logistic regression model (model 1). Though we can see that model 1 has a better precision score, model 2 shows less variance between the f1-score between class labels. Additionally, model 2 has a strong recall score compared to model 1. Between the two models above, I would choose model 2 with the oversampled data. However, I believe detecting fraud is the problem we are trying to solve and believe there is a different machine learning model might work better with this particular testing and training dataset. 


