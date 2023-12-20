# Credit-Risk-Classification

Module 20 Challenge: UWA/edx Data Analytics Bootcamp

Github repository at: https://github.com/RyanLJames1997/Credit-Risk-Classification

## Introduction

## Scope

In this challenge, as a data analyst, a variety of techniques will be implemented to train and evaluate a model based on `loan risk` based on a historical lending dataset. 

The historical data is sourced from a peer-to-peer lending services company.

- Historical data, and features include:
  
        - Loan size
        - Interest rates
        - Borrower income
        - Debt to income ratio
        - Number of accounts
        - Derogatory remarks
        - Total debt
        - Loan status

Furthermore, the `loan_status` column will be used as the `target`, and the remaining columns will be identified as `features` in this supervised `machine_learning` prediction model.

### Goal

The overall goal of this analysis is to see if we can predict whether a credit loan is `healthy` or `high-risk` using the **logistic regression** method. 

### Repository Structure

- The root directory that contains the source code: `credit_risk_classification.ipynb` from the `Scikit-learn_Library`.

- The `Resources` directory contains the raw dataset used in the model 

### Dataset

The dataset was generated by the team at **edX Boot Camps LLC** and **Mockaroo LLC 2022**

## Approach
1. Split the Data into **training** and **testing**.
   - Read the raw data into a `Pandas` Dataframe.
   - Seperate the X-variables **(features)** and y-variables **(labels)**.
   - Use the code `train_test_split`to split the data.
  
2. Create a **Logistic Regression Model** with the original data.
   - Fit a logistic regression model by using the training data (X_train and y_train).
   - Save the predictions for the testing data labels by using the testing feature data (X_test) and the fitted model.
   - Evaluate the model’s performance by doing the following:
        - Generate a confusion matrix.
        - Print the classification report.
    
## Results
The **Logistic Regression Model** output yielded the following results:

| Class           | Precision | Recall | F1-Score | Support |
|-----------------|-----------|--------|----------|---------|
| healthy loan    | 1.00      | 1.00   | 1.00     | 18765   |
| high-risk loan  | 0.87      | 0.89   | 0.88     | 619     |
| accuracy        |           |        | 0.99     | 19384   |
| macro avg       | 0.94      | 0.94   | 0.94     | 19384   |
| weighted avg    | 0.99      | 0.99   | 0.99     | 19384   |

Through observation of the models yeilded results, it was able to predict both the `healthy (0)` and `high-risk (1)`labels with 99% accuracy score.

- `healthy loan (0)`: The F1-score had a computed value of 100%, as both the **precision** and **recall** values were also at 100%.

- `high-risk loan (1)`: The F1-score had a computed value of 88%. This was slightly less accurate, as both the **precision** and **recall** were 87% and 89% respectably. This lower accuracy level is likely due to fewer records in relation to the sample size, as the `high-risk loan (1)` label had 2,500 records in comparison to the `healthy loan (0)` label with 75,036 records.

## Summary
In conclusion, the **Logistic Regression** model was able to demonstrate an overall accuracy level of 99% when looking at the labels of `healthy loans (0)` and `high-risk loans (1)`. 

There was an inbalance across the dataset which likely skewed the overall accuracy in favour off the `Healthy loans (0)` with a much greater number of records. Due to the high skewness of the classes, the minority class is a **moderate** degree of imbalance - thus, the training model will spend more time assessing on the majority class. Furthermore, a deeper way to handle this imbalanced data is to downsample and upweight the downsampled class `Risky loans loans (1)`.

- Downsampling: infers data analysts to train the data set by a key factor to improve the overall balance and skew the results closer together.
- Upweight the downsampled class: Increase the overall weighting of the inferrior class. This will add additional parameters to the neural network. This in essence will:
  
    - Yeild faster convergence across the model and upweighting with ensure the model is still functional and callibrated correctly.
  
Lastly, the model was only tested based on the `otiginal data` - thus, did not factor any `null_values`. An additional reccomendation would be to `scale` the data to see if this improves overall accuracy of the model. However, the overall high accuracy and optimised tradeoff between these two labels to strong. 

## References
- Coding and terminology was derived from **Bootcamp Week 5**
- **Chat GPT**
- `Imbalanced Data` from developers.google.com: https://developers.google.com/machine-learning/data-prep/construct/sampling-splitting/imbalanced-data
