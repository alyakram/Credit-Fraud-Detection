Credit Fraud detection:

Context:
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.


Dataset Location : This dataset could be found at https://www.kaggle.com/mlg-ulb/creditcardfraud


This dataset (creditcard.csv) was provided by KAGGLE
The dataset contains transactions made by credit cards in September 2013 by European cardholders. 
It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

This dataset is already preprocessed.

I began with splitting the dataset into train and test sets with a split of 0.75:0.25,
Did a brief analysis and checked that the dataset contains 99.8% of the values are labeled as not fraud and only 0.2% are labeled as fraud.
I bootstrapped the data by upsampling the training dataset because if we had only a few positives relative to negatives, the training model will spend most of its time on negative examples and not learn enough from positive ones. Therefore I bootstrapped the data to make it balanced.

Then I applied Random Forest with the number of trees = 20 and determined which were the most important features for our model.

I followed with Logistic Regression

Then finally I followed by a Gaussian Naive Bayes

I tested all three models for accuracy, precision, recall and f1 score.

The Random Forest model has better accuaracy and precision than the Logistic Regression and Gaussian Naive Bayes models, but Logistic regression has the best recall, yet Random Forest has the best f1 score which is the harmonic average between precision and recall.

