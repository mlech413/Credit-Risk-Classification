# Credit-Risk-Classification

## Analysis Overview

This analysis used various techniques to train and evaluate a model based on loan risk. Dataset "Resources/lending_data.csv" contains historical lending activity from a peer-to-peer lending services company. A model was built in Jupyter Notebook file "credit_risk_classification.ipynb" that identified the creditworthiness of borrowers.  

The following was performed:
* The data was split into training and testing sets. Column "loan_status" was split out and contained 0 (for healthy loans) and 1 (high-risk loans). "value_counts" identified 75,036 healthy loans and 2,500 high-risk.
* A logical regression model was created with the original training data by removing 25% of the results and then using LogisticRegression to train the model. The resulting balanced accuracy score, confusion matrix, and classification report were used to check the results.
* A logical regression model was also predicted with resampled training data by using the RandomOverSampler module from the imbalanced-learn library to resample the data. The minority samples (high-risk loans) were duplicated and increased to match the 75,036 healthy loan samples. The modeling process was then repeated with this data, and the balanced accuracy score, confusion matrix, and classification report were used to check the results.

## Results

### Machine learning model 1 - logical regression model with the original training data

The logical regression model is a very good predictor of healthy loans:  

  * A strong balanced accuracy score of 95.2%.
  * High precision scores show that out of all the loans that the model predicted as heathly, all 100% actually were, while 85% of the predicted high-risk loans actually were.
  * Similarly high recall values show that of all the loans that eventually proved to be healthy, the model correctly predicted this 99% of the time, and also predicated 91% of the high risk loans.
  * A weighted average F1 score of 99% demonstrates an extremely high combination of both precision and recall.

   ![Classification Report - Original](/Images/Classification_Report_Original.jpg "Classification_Report_Original")

  * The confusion matrix further confirms the high reliability of the model.

  ![Confusion Matrix - Original](/Images/Confusion_Matrix_Original.jpg "Confusion Matrix - Original")


### Machine learning model 2 - logical regression model with oversampled data

When fitting the logical regression model with oversampled data, the model's accuracy showed dramatic improvement in all categories.  

  * The balanced accuracy score rose from 95.2% to 99.5%.
  * The classification report resulted in weighted averages of 100% in all categories (precision, recall and f-1 score).

   ![Classification Report - Oversampled](/Images/Classification_Report_Oversampled.jpg "Classification_Report_Oversampled")

  * The confusion matirx showed extremely high accuracies.

  ![Confusion Matrix - Oversampled](/Images/Confusion_Matrix_Oversampled.jpg "Confusion Matrix - Oversampled")

## Summary

The oversampled model performed better than the original data model. However, it cannot be recommended because further reasearch is needed to determine if the increased accuracy is due to such a high number of duplicated high-risk samples, which may have forced the model to contain too many similar rows. For this reason, the oversampled model cannot be used until such the large amount of oversampled data can be determined to be effective and accurate. Increasing the "1" (high-risk) rows from 2,500 to over 75,000 seems excessive, especially given that the high-risk "1" rows are the most potentially financially damaging and therefore most important. Until that time, the original data modfel with a lower (although very still high) accuracy should be used with greater confidence.
