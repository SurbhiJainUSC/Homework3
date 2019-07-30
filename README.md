# Time-Series-Classification

The task is to classify the activities of humans based on time series obtained by a Wireless
Sensor Network.

## Dataset
The Activity Recognition system based on Multisensor data fusion (AReM) Dataset contains 7 folders 
that represent seven types of activities. In each folder, there are multiple files each of which 
represents an instant of a human performing an activity. Each file contain 6 time series collected 
from activities of the same person, which are called avg rss12, var rss12, avg rss13, var rss13,
vg rss23, and ar rss23. There are 88 instances in the dataset, each of which contains
6 time series and each time series has 480 consecutive values. <br/>
The datasets 1 and 2 in folders bending1 and bending 2, as well as datasets 1, dataset 2, and dataset 3
in other folders are considered as testing data and other datasets are considered as training data.

## Feature Extraction
Classification of time series usually needs extracting features from them. So, extract the time-domain features 
such as minimum, maximum, mean, median, standard deviation, first quartile, and third quartile for all the 6 time 
series in each instance. Estimate the standard deviation of each of the time-domain features, 90% bootsrap confidence 
interval for the standard deviation of each feature to select the three most important time-domain features.

## Binary Classification using Logistic Regression
The task is to classify bending activities (bending1 and bending2) from other activities using logistic regression.
Break each time series in training set into l=1 to 20 time series of approximately equal length and use logistic 
regression to solve the binary classification problem using time-domain features. Calculate the p-values for 
logistic regression parameters in each model corresponding to each value of l. Use 5-fold stratified cross-validation 
to determine the best value of the pair (l, p), where p is the number of features used in recursive feature elimination.

## Binary Classification using L1-Penalized Logistic Regression
The task is to classify bending activities (bending1 and bending2) from other activities using L1-penalized 
logistic regression. Break each time series in training set into l=1 to 20 time series of approximately equal 
length and use logistic  regression to solve the problem. Calculate the p-values for 
logistic regression parameters in each model corresponding to each value of l. Use 5-fold stratified cross-validation to cross-validate for both l, 
the number of time series into which you break each of your instances, and the weight of L1 penalty in logistic
regression objective function.

## Multiclass Classification
The task is to classify seven types of activities using Gaussian Naive Bayes classifier and Multinomial 
Naive Bayes classifier and compare the results.
