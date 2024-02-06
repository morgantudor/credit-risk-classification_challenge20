Challenge 20: Credit Risk Classification

## Overview of the Analysis
The purpose of this analysis was to build a model that can identify the creditworthiness of borrowers through analysis of historical peer-to-peer lending services. The dataset included borrower information like their borrowed loan amount, interest rates, and aspects of their credit history. This information helped to categorize borrowers and their loan status as healthy or high risk. 

There were multiple variables accounted for within our model. The dependent variable was the loan status indicating whether a borrow has a healthy loan status or a high risk loan status. There were other independent variables that would help us to predict the dependent variable like loan size, interest rate, income-to-debt ratio, derogatory marks, and number of accounts open. Training our model to analyze these aspects and distinguish between which variables would make a borrow more likely to be high risk would help protect our company from potential high risk financial decisions.

To begin this analysis, the data was split into training and test sets. We then fit the model with the training data to train it on our various variables. We made predictions based on our testing data and then confirmed the accuracy of those results. 

After determining there was an imbalance of data types in our original dataset, we performed the same logistic regression with resampled training data to hopefully balance the training set we provided to our training set. We used RandomOverSampler to perform this, fit the model, and then predicted again and analyzed those results.


## Results
* Machine Learning Model 1:
  Balanced Accuracy Score: 0.952

  0 (healthy loan):
    precision score: 1.00
    recall score: 1.00

  1 (high-risk loan):
    precision score: 0.86
    recall score: 0.90


* Machine Learning Model 2:
  Balanced Accuracy Score: 0.994
  
  0 (healthy loan):
    precision score: 1.00
    recall score: 0.99

  1 (high-risk loan):
    precision score: 0.84
    recall score: 0.99


## Summary
Overall, the first model shows an accuracy rate of 0.99 which would seem like a well fit model. Looking closer, the healthy loan prediction, score 0, shows a 1.00 precision rate while high risk loan prediciton, score 1, shows 0.86. The higher precision rate is important because it will ensure the model isn't giving too many false positives. The recall rates aren't too bad either, at 1.00 for the healthy loans and 0.90 for high risk. High recall scores minimize false negatives. While all of this may look promising (less so for the high risk loan predictions, but still high), it's important to note that our model may not be properly fit and trained as there is a large imbalance in healthy loans/high risk loans in the data set. A better model could be made using resampled data.

Like the previous model, our resampled report shows and accuracy rate of 0.99, which is high. Upon closer inspection, we can see that the balanced accuracy score has increased from 0.95 to 0.99 which shows it is more effective that the previous model. We can also see that the recall scores on the high risk loans has improved from 0.90 to 0.99 and the f1 scores have increased from 0.88 to 0.91. This would suggest that the oversampled data improves upon the first model and is, therefore, more effective at distinguishing between loan types.

Our analysis show that for better preditions solving the imbalance sampling issue is needed. Randomly oversampling the data helps us to get higher balanced accuracy and recall scores. With higher recall value, model can predict risky loans more accurately. Without this consideration, we may run into two issues. The first would be false positives, where borrowers would be flagged as high-risk but would actually be well suited borrowers. The other would be false negatives, where borrowers would be flagged as healthy, but in turn likely default on their loan. Both scenarios are troublesome. One would drive away business from borrowers that a business wants to attract and the other would but the business at risk of not getting a return on their investment. It's important in this sort of high-risk situation to find a model that accurately predicts both high-risk and healthy loan status. Our model seems to do a fairly good job at both, with room to grow and refine the learning in the high risk category.
