# Loan-Default-Prediction
A major proportion of retail bank profit comes from interests in the form of home loans. These loans are borrowed by regular income/high earning customers. Banks are most fearful of defaulters, as bad loans (NPA) usually eat up a major chunk of their profits. Therefore, it is important for banks to be judicious while approving loans for their customer base.

* Build a classification model to predict clients who are likely to default on their loan
* Give recommendations to the bank on the important features to consider while approving a loan. 


### **Reminder of Objectives**

* Build a classification model to predict clients who are likely to default on their loan
    * Maximizing `Recall` (false negatives) as banks are more fearfull of defaulters given they result in greater loss. 
    * Preferably maintaining a high `F1-Score` (overall accuracy) as false positives would result in a loss of interest profit for the bank. 
* Give recommendations to the bank on the important features to consider while approving a loan. 

### **Conclusions:**
#### **Model Performance**
It became clear as we refined the models that the size (5960 data points) and composition (80/20 non-defaulters to defaulters) of the dataset was contributing to lower that ideal accuracy scores. Therefore, our initial objective of maximizing recall and maintaining a high f1-score was unlikely, and therefore we shifted to **focus solely on maximizing recall** even at the expense of overall accuracy. 

We built multiple decision tree based models that can predict if a loan is likely to default, of those two models performed and generalized well:
* Tuned Decision Tree Model - f1-score 67% and recall 75%
* Hyper Tuned Random Forest Model - f1-score 60% and recall 80%

The two models are evenly balanced, with the tuned model being leaning more towards overall accuracy and the random forest model leaning more towards recall. For the reasons stated above it is preferable to maximize recall even at the expense of accuracy, therefore, it is **recomended we use the Hyper Tuned Random Forest Model**.

With the challenge of a limited dataset, we were able to successfully able to tune our model to maximize a **recall score of 80%.**

--------------------------------
#### **Feature Importance**

Looking at feature importances, we can say that **`DEBTINC` (Debt-to-income ratio)** is a dominant predictor of defaulters, where a higher DEBTINC indicates the applicant is more likely to default. This makes sense as applicants who owe more money than they are bringing are likely to struggle with paying off any new loans.

The only other features that showed significant impact are: `CLAGE`, `VALUE`, `NINQ` and `Loan`. All other features showed little to no impact on predicting defaulters.
* Where a lower `VALUE` is more likely to default
* Where a lower `CLAGE` is more likely to default
* Where a higher `NINQ` is more likely to default
* Where a lower `Loan` is more likely to default
--------------------------------
#### **Exploratory Data Analysis**

While `DEROG` and `DELINQ` did not show a high feature impact, EDA clearly showed that a DEROG>6 and DELINQ>5 always resulted in a default. Further it showed that it was only in a few cases that that the bank gave out loans to those with a `DEROG` and `DELINQ` greater than 0.

EDA also showed that the different cathegories of `JOB` had reletively equal percentages of defaulters.
