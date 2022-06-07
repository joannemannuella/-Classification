# Unit 11 Homework - Risky Business
 
![Credit Risk](Images/credit-risk.jpg)

## Background

Mortgages, student and auto loans, and debt consolidation are just a few examples of credit and loans that people seek online. Peer-to-peer lending services such as Loans Canada and Mogo let investors loan people money without using a bank. However, because investors always want to mitigate risk, a client has asked that you help them predict credit risk with machine learning techniques.

In this assignment you will build and evaluate several machine learning models to predict credit risk using data you'd typically see from peer-to-peer lending services. Credit risk is an inherently imbalanced classification problem (the number of good loans is much larger than the number of at-risk loans), so you will need to employ different techniques for training and evaluating models with imbalanced classes. You will use the imbalanced-learn and Scikit-learn libraries to build and evaluate models using the two following techniques:

1. Resampling

2. Ensemble Learning

- - -

## Analysis :

[Resampling Notebook](https://github.com/joannemannuella/Classification/blob/main/Analysis/credit_risk_resampling.ipynb)

[Ensemble Notebook](https://github.com/joannemannuella/Classification/blob/main/Analysis/credit_risk_ensemble.ipynb)



- - -



### Resampling

Use the [imbalanced learn](https://imbalanced-learn.readthedocs.io) library to resample the LendingClub data and build and evaluate logistic regression classifiers using the resampled data.

To begin:

1. Read the CSV into a DataFrame.

2. Split the data into Training and Testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.

4. Use the provided code to run a Simple Logistic Regression:
    * Fit the `logistic regression classifier`.
    * Calculate the `balanced accuracy score`.
    * Display the `confusion matrix`.
    * Print the `imbalanced classification report`.

Next I did the following:

1. Oversample the data using the `Naive Random Oversampler` and `SMOTE` algorithms.

2. Undersample the data using the `Cluster Centroids` algorithm.

3. Over- and undersample using a combination `SMOTEENN` algorithm.


For each of the above, I need to:

1. Train a `logistic regression classifier` from `sklearn.linear_model` using the resampled data.

2. Calculate the `balanced accuracy score` from `sklearn.metrics`.

3. Display the `confusion matrix` from `sklearn.metrics`.

4. Print the `imbalanced classification report` from `imblearn.metrics`.


Use the above to answer the following questions:

1. Which model had the best balanced accuracy score?

   **SMOTEENN(Combination under and over sampling), Naive Random Oversampling and SMOTE have the higest accuracy score of 0.9946414201183431 in percentage closer to 100%**

2. Which model had the best recall score?

    **All the model have the same avarege recall score alothough for undersampling is equal amount of recall high_risk of 0.99 and low_risk 0.99**
3. Which model had the best geometric mean score?

   **All the model have the same avarege geometric score of   0.99**


### Ensemble Learning

In this section, you will train and compare two different ensemble classifiers to predict loan risk and evaluate each model. You will use the [Balanced Random Forest Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.BalancedRandomForestClassifier.html) and the [Easy Ensemble Classifier](https://imbalanced-learn.org/stable/references/generated/imblearn.ensemble.EasyEnsembleClassifier.html). Refer to the documentation for each of these to read about the models and see examples of the code.

To begin:

1. Read the data into a DataFrame using the provided starter code.

2. Split the data into training and testing sets.

3. Scale the training and testing data using the `StandardScaler` from `sklearn.preprocessing`.


Then, I completed the following steps for each model:

1. Train the model using the quarterly data from LendingClub provided in the `Resource` folder.

2. Calculate the balanced accuracy score from `sklearn.metrics`.

3. Display the confusion matrix from `sklearn.metrics`.

4. Generate a classification report using the `imbalanced_classification_report` from imbalanced learn.

5. For the balanced random forest classifier only, print the feature importance sorted in descending order (most important feature to least important) along with the feature score.


Use the above to answer the following questions:


1. Which model had the best balanced accuracy score?

  **Both Model have same accuracy score , in my analysis the reason being the data normalisation using StandardScaler function**

2. Which model had the best recall score?

  **Both Model has 67% recall score for high_risk and 0.91 for low_risk**

3. Which model had the best geometric mean score?

  **Both model have 78% of geometric mean score**

4. What are the top three features?

**total_rec_prncp for 0.07376667607601396**

**total_rec_int for  0.06390324452717588**

**total_rec_int' for 0.06073336071656837**

- - -
