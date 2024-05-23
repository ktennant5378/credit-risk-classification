# Credit Risk Report

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* The purpose of this analysis is to classify loans as risky or safe using a number of factors listed below 
    * loan_size: dollar amount of the loan the customer was taking out 
    * interest_rate: Interest rate of the loan 
    * borrower_income: How much money per year the borrower made
    * debt_to_income: Ratio of the total debt/ borrower's income
    * num_of_accounts: How many loans the borrower has
    * derogatory_marks: Whether or not the borrower has recieved derogatory marks (late payments, defaults, bankruptcy etc.)
    * total_debt: Sum of all the debt the borrower is borrowing
    * loan_status: Whether or not the loan is healthy or at risk of default (0:Healthy 1:Risk of Default)
* In this analysis we are trying to predict the loan_status (whether the loan will be risky or safe) based on the above variables. 
* Describe the stages of the machine learning process you went through as part of this analysis.
    * 1: Split the data into training and testing data. We use the training data to fit our model then test how accurate the model can predict the loan's status using the test data. 
    * 2: Fit a logistic regression model using the train data then predict the loan status of the testing data. 
    * 3: Evaluate the model's performance using a confusion matrix and a classification report. This report shows how accurate the model is at predicting the loan status
* We used logistic regression to predict the loan's status. Logistic regression predicts the probability of a binary outcome (1 or 0) which makes it perfect for this classification problem we have. In this case, we take a number of features and the model will give it a probability score based on the training data (>0.5 = 1, <.5 = 0). 

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
    * Accuracy: (TruePositives+TrueNegatives)/(TruePositives+TrueNegatives+FalsePositives+FalseNegatives)
        * Total Accuracy = 0.99. This means 99% of the predictions were correctly classified. 
    * Pecision: TruePositives/(TruePositives+FalsePositives)
        * Safe Loans = 1.00. This indicates there were no false positives when classifying safe loans, meaning all loans predicted as safe were safe loans.  
        * Risky Loans = 0.85. This indicates that there were false positives when predicting risky loans. This means that loans that were safe were classified as risky.
    * Recall: TruePositives/(TruePositives+FalseNegatives)
        * Safe Loans = 0.99. This means 99% of all safe loans were correctly classified
        * Risky Loans = 0.91. This means 91% of all risky loans were classified correctly, 9% were false negatives.
## Summary

The model does boast a 99% accuracy and seems to flag safe loans as risky, which is better than flagging risky loans as safe. This being said, a better model would predict both accuratly and it looks like this might be due to the difference in the category counts. Before splitting the data, there were 75,036 safe loans with only 2,500 risky loans, 3% of the loans were risky in the dataset. This discrepency is why there appears to be a bias towards safe loans, it was trained with way more safe loans than risky loans. I wouldn't reccomend using this model as it is, instead training the model with a greater number of risky loans to help eliminate that bias. 
