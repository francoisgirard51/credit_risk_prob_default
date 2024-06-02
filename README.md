# Credit ccoring project

This project focuses on developing a predictive model to estimate the probability of an individual facing financial distress within a two-year timeframe. Credit scoring is a crucial tool used by banks to make informed lending decisions, influencing both the accessibility and terms of finance. The accuracy of these models plays a significant role in the economic and social fabric, affecting investment decisions and the overall functionality of market economies.

## Table of contents
1. [Data](#data)
2. [Data collection & preprocessing](#data-collection--preprocessing)
3. [Data cleaning](#data-cleaning)
4. [Data imputation](#data-imputation)
5. [Model preparation](#model-preparation)
6. [Model training](#model-training)
7. [Model evaluation](#model-evaluation)
8. [Conclusion](#conclusion)

## Data
The project involves three primary datasets, each offering different perspectives and data points crucial for developing the predictive model:

### 1. Training data (cs-training.csv)
- `SeriousDlqin2yrs`: The person experienced 90 days past due delinquency or worse (Yes = 1, No = 0).
- `RevolvingUtilizationOfUnsecuredLines`: Total balance on credit cards and personal lines of credit except real estate and no installment debt like car loans divided by the sum of credit limits.
- `age`: Age of borrower in years.
- `NumberOfTime30-59DaysPastDueNotWorse`: The number of times borrower has been 30-59 days past due but no worse in the last 2 years.
- `DebtRatio`: Monthly debt payments, alimony, and living costs divided by month gross income.
- `MonthlyIncome`: Monthly income.
- `NumberOfOpenCreditLinesAndLoans`: The number of open loans (installment like car loan or mortgage) and credit lines (e.g., credit cards).
- `NumberOfTimes90DaysLate`: Number of times borrower has been 90 days or more past due.
- `NumberRealEstateLoansOrLines`: Number of mortgage and real estate loans including home equity lines of credit.
- `NumberOfTime60-89DaysPastDueNotWorse`: Number of times borrower has been 60-89 days past due but no worse in the last 2 years.
- `NumberOfDependents`: Number of dependents in the family excluding themselves (spouse, children, etc.).

### 2. Test data (cs-test.csv)
The test dataset shares the same structure as the training dataset but does not include the `SeriousDlqin2yrs` outcome variable, as it is used to assess the model's performance on unseen data.

### 3. Sample submission (sampleEntry.csv)
This file provides a template for submitting predictions. It contains two columns:
- **Id**: A unique identifier for each instance in the test set.
- **Probability**: The predicted probability of the event `SeriousDlqin2yrs` occurring.

## Data collection & preprocessing
- **Importing libraries**: Required libraries include pandas, numpy, seaborn, and matplotlib.
- **Loading data**: Training and test datasets are loaded and unnecessary columns are dropped.
- **Initial inspection**: The first few rows of the dataset are inspected to understand its structure.

## Data cleaning
- **Duplicate check**: Checking for and removing duplicate rows.
- **Missing value analysis**: Calculating the percentage of missing values in each column.

## Data imputation
- **Handling missing values**: Filling missing values for `NumberOfDependents` with 0 and for `MonthlyIncome` with the median.
- **Combining data**: Merging the filled datasets and ensuring no missing values remain.

## Model preparation
- **Model initialization**: Using the XGBoost classifier.
- **Feature and target Preparation**: Preparing the features (X) and target (y) for training.

## Model training
- **Training the Model**: Fitting the model on the training data.

## Model evaluation
- **Predictions**: Making predictions on the training set.
- **Accuracy score**: Calculating the accuracy of the model.
- **Confusion matrix**: Visualizing the confusion matrix with a heatmap.
- **Classification report**: Generating a detailed classification report including precision, recall, and F1-score.

## Conclusion
The model demonstrates high accuracy and precision in predicting loan repayment, with an overall accuracy of 94.65%. However, it shows a lower recall for the default class, indicating room for improvement in detecting defaults. The model serves as a robust starting point for identifying and managing credit risk, with suggestions for further refinement to enhance its utility in real-world applications.
