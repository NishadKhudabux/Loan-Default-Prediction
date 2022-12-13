# Loan-Default-Prediction
## ### **Context:**
A major proportion of retail bank profit comes from interests in the form of home loans. These loans are borrowed by regular income/high earning customers. Banks are most fearful of defaulters, as bad loans (NPA) usually eat up a major chunk of their profits. Therefore, it is important for banks to be judicious while approving loans for their customer base.

* Perform EDA and give recommendations to the bank on the important features to consider while approving a loan.
* Build a classification model to predict clients who are likely to default on their loan
    * Maximizing `Recall` (false negatives) as banks are more fearfull of defaulters given they result in greater loss. 
    * Preferably maintaining a high `F1-Score` (overall accuracy) as false positives would result in a loss of interest profit for the bank. 
--------------------------------
#### **Results**
With the challenge of a limited dataset, we were able to successfully able build and tune a Hyper Tuned Random Forest Model to maximize **recall score of 80%.**

Found that **`DEBTINC` (Debt-to-income ratio)** is a dominant predictor of defaulters, along with 4 other key features `CLAGE`, `VALUE`, `NINQ` and `Loan`.

From our model and EDA we identified 4 high impact buisness recommendations moving forward.
