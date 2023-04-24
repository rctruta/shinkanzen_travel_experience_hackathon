# Shinkanzen Travel Experience Hackathon

### Problem Definition

This problem statement is based on the Shinkansen Bullet Train in Japan, and passengers’ experience with that mode of travel. This machine learning exercise aims to determine the relative importance of each parameter with regards to their contribution to the passengers’ overall travel experience. The dataset contains a random sample of individuals who traveled on this train. The on-time performance of the trains along with passenger information is published in a file named ‘Traveldata_train.csv’.  These passengers were later asked to provide their feedback on various parameters related to the travel along with their overall experience. These collected details are made available in the survey report labeled ‘Surveydata_train.csv’.

In the survey, each passenger was explicitly asked whether they were satisfied with their overall travel experience or not, and that is captured in the data of the survey report under the variable labeled ‘Overall_Experience’. 

### Objectives

The objective of this problem is to understand which parameters play an important role in swaying passenger feedback towards a positive scale. You are provided test data containing the travel data and the survey data of passengers. Both the test data and the train data are collected at the same time and belong to the same population.

The goal of the problem is to **predict whether a passenger was satisfied or not** considering his/her overall experience of traveling on the Shinkansen Bullet Train.

### Results

The final proposed solution is an ensemble Histogram-based Gradient Boosting algorithm [1] that works with data imputed with Iterative Imputer [2] by modeling each feature with missing values as a function of other features. Hyperopt [3] was used to optimize parameters of the estimator, reaching an accuracy of 95.09%.

[1] Scikit-learn developers. HistGradientBoostingClassifier: scikit-learn 0.24.2 documentation. Retrieved April 24, 2023, from https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingClassifier.html.

[2] Scikit-learn developers. IterativeImputer: scikit-learn 0.24.2 documentation. Retrieved April 24, 2023, from https://scikit-learn.org/stable/modules/generated/sklearn.impute.IterativeImputer.html

[3] Bergstra, J., Yamins, D., & Cox, D. D. Hyperopt: A Python library for optimizing the hyperparameters of machine learning algorithms. Retrieved April 24, 2023, from http://hyperopt.github.io/hyperopt/

# Data 

The problem consists of 2 separate datasets: Travel data & Survey data. Travel data has information related to passengers and attributes related to the Shinkansen train, in which they traveled. The survey data is aggregated data of surveys indicating the post-service experience. You are expected to treat both these datasets as raw data and perform any necessary data cleaning/validation steps as required.

The data has been split into two groups and provided in the Dataset folder. The folder contains both train and test data separately.

 - Train_Data
 - Test_Data

Target Variable: Overall_Experience (1 represents ‘satisfied’, and 0 represents ‘not satisfied’)

The training set can be used to build your machine learning model. The training set has labels for the target column - Overall_Experience.

The testing set should be used to see how well your model performs on unseen data. For the test set, it is expected to predict the ‘Overall_Experience’ level for each participant.

# Environment

Activate with `conda env create -f shinkanzen_travel_experience.yml`.
