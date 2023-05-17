# Credit-Risk-Classification

## Analysis Overview

This analysis used various techniques to train and evaluate a model based on loan risk. Dataset "Resources/lending_data.csv" contains historical lending activity from a peer-to-peer lending services company. A model was built in Jupyter Notebook file "credit_risk_classification.ipynb" that identified the creditworthiness of borrowers.  

The following was performed:
* The data was split into training and testing sets. Column "loan_status" was split out and contained 0 (for healthy loans) and 1 (high-risk loans). "value_counts" identified 75,036 healthy loans and 2,500 high-risk.
* A logical regression model was created with the original training data by removing 25% of the results and then using LogisticRegression to train the model. The resulting balanced accuracy score, confusion matrix, and classification report were used to check the results.
* A logical regression model was also predicted with resampled training data by usiong the RandomOverSampler module from the imbalanced-learn library to resample the data. The minority samples (high-risk loans) were duplicated and increased to match the 75,036 healthy loan samples. The medeling process was then repeated with this data, and the alanced accuracy score, confusion matrix, and classification report were used to check the results.

## Results

* Machine learning model 1 - logical regression model with the original training data:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine learning model 2 - logical regression model with oversampled data:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.