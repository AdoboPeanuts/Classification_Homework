# Unit 11 - Risky Business
 
![Credit Risk](Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked that you help them predict credit risk with machine learning techniques.

In this assignment I will build and evaluate several machine learning models to predict credit risk using data we would typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), I will need to employ different techniques for training and evaluating models with imbalanced classes. I will use the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. [Resampling](#Resampling)
2. [Ensemble Learning](#Ensemble-Learning)

- - -

## Files

[Resampling Starter Notebook](credit_risk_resampling.ipynb)

[Ensemble Starter Notebook](credit_risk_ensemble.ipynb)

[Lending Club Loans Data](Resources/LoanStats_2019Q1.csv.zip)

- - -

## Process & Workflow

### Resampling

Imported [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data. The library will serve as a unit to build and evaluate logistic regression classifiers using the resampled data.

First Phase:

1. Read the CSV into a DataFrame.

2. Split the data into Training and Testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. Used the provided code to run a Simple Logistic Regression:
    * Fit the `logistic regression classifier`.
    * Calculated the `balanced accuracy score`.
    * Displayed the `confusion matrix`.
    * Printed the `imbalanced classification report`.

Second Phase:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms;

    a. Trained a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

    b. Calculated the `balanced accuracy score` from `sklearn.metrics`.

    c. Displayed the `confusion matrix` from `sklearn.metrics`.

    d. Printed the `imbalanced classification report` from `imblearn.metrics`.

2. Undersample the data using the `Cluster Centroids` algorithm;

    a. Trained a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

    b. Calculated the `balanced accuracy score` from `sklearn.metrics`.

    c. Displayed the `confusion matrix` from `sklearn.metrics`.

    d. Printed the `imbalanced classification report` from `imblearn.metrics`.

3. Over and undersample using a combination `SMOTEENN` algorithm;

    a. Trained a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

    b. Calculated the `balanced accuracy score` from `sklearn.metrics`.

    c. Displayed the `confusion matrix` from `sklearn.metrics`.

    d. Printed the `imbalanced classification report` from `imblearn.metrics`.

---

## Results

Q1. Which model had the best balanced accuracy score?

    A: Both naive over sampling and smote over sampling model has the best balanced accuracy score at 99.37% 

Q2. Which model had the best recall score?

    A: Both naive over sampling and smote over sampling model has the best balanced accuracy score at 99.38% 

Q3. Which model had the best geometric mean score?

    A: Both naive over sampling and smote over sampling model has the best geometric mean score at 99.37%.

---
### Ensemble Learning

In this section, I will train and compare two different ensemble classifiers to predict loan risk and evaluate each model. I will use the [Balanced Random Forest Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.BalancedRandomForestClassifier.html) and the [Easy Ensemble Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.EasyEnsembleClassifier.html). Refer to the documentation for each of these to read about the models and see examples of the code.

First Phase:

1. Read the data into a DataFrame using the provided starter code.

2. Split the data into training and testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Second Phase:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculated the balanced accuracy score from `sklearn.metrics`.

3. Displayed the confusion matrix from `sklearn.metrics`.

4. Generated a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. Printed the feature importance the balanced random forest classifier, sorted in descending order (most important feature to least important) along with the feature score.


---

Q1. Which model had the best balanced accuracy score?

    A: The Easy Ensemble Classifier has the best balanced accuracy score at 99.32% 

Q2. Which model had the best recall score?

    A: The Easy Ensemble Classifier has the best recall score at 99.28%

Q3. Which model had the best geometric mean score?

    A: The Easy Ensemble Classifier has the best geometric mean score at 99.32%.

Q4. What are the top three features?


    A: The top three features initialized by the Balanced Random Forest Classifier;
    
        i. Debt to income (21.79%)
   
        ii. Interest Rate (19.59%)

        iii. Borrower Income (16.88%)

---



