# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.

The analysis was aimed to use a logistic regression model to compare two versions of the dataset of interest. We analyzed the data as is and the data with random oversampling processing. We pursued these two types of analyses to optiize for the inherently imbalnaced nature of credit risk classification in which healhty loans tend to outnumber risky loands

* Explain what financial information the data was on, and what you needed to predict.

The financial information included in the data were loan size, interest rate, borrower income, det to income ratio, number of accounts, derogatory marks, total debt and loan status classification. We reated a logistic regression model with the original data. We needed to predict a logistic regression model with resampled training data.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

The variables we were trying to predict were loan status. We were looking at healthy loans and risky loans classified as '0' and '1'

* Describe the stages of the machine learning process you went through as part of this analysis.
The general stages of the machine learning process we employed include:
1) read the respective ldata from the csv file (or other data source)

2) separating the data into labels and features
  - the features being the variables to be predicted and y being the independent variable/labels

3) Checking the balance of the labels variable by using the variable count function

4) splitting the data into training and testing datasets via the train_test_split function
  - this involves splitting the data into X_train, X_test, y_train, and y_test variable assignments

5) Creating the regression model for modeling and further predictions
  - here we set up an instance of the model with a random state for seeding
  - we then fit the model
  - we then perform the prediction

6) We evaluate the performance of the model
  - this is with a confusion matrix and classification report in our case

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
- We used the LogisticRegression(), RandomOverSampler(), methods for the fitting and modeling
- the RandomOverSampler method was responsible for resampling the imbalanced credit data

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  * model 1 was the logistic regression model with the original data
    * Balanced Accuracy Score: 0.952
    * Precision:
      * class 0 healthy loan: 1.00
      * class 1 risky loan: 0.85
    * Recall:
      * class 0 healthy loan: 0.99
      * class 1 risky loan: 0.91
    * Description:
      * all of these scores were pretty high showing high accuracy, precision and recall for the groups
      * the precision for the risky loan was the lowest score at 0.85

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  * model 2 was a logistic regression model with resampled training data using random over sampler dependency
    * Balanced Accuracy Score: 0.9937
    * Precision:
      * class 0 healthy loan: 1.00
      * class 1 risky loan: 0.84
    * Recall:
      * class 0 healthy loan: 0.99
      * class 1 risky loan: 0.99
    * Description
      * all of these scores are very high, even higher with the resampling
      * the precision score for the risky loan was the lowest score at 0.84

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
  The resampling method did improve the performance of the regression model. As seen above, the balanced accuracy score of the second machine learning model is higher, the precision and recall values are either the same or better except for the one specific presicion score for the class 1 group which is a hair lower. 

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? ) 

  Performance does seem to depend on the problem being solved. In this case it's more important to predict the '1's relatively because that is the undersampled group. This is because, as stated in the initial propmt, healthy loans outnumber risky loans significantly. Also as we can see from the precision scores of both of these models, the risky loans have the lowest precision scores. This certainly needs to be considered in the analysis.

If you do not recommend any of the models, please justify your reasoning.
  
  I do recommend these models.
