---
title: "CodeBook"
author: "Nasim"
date: "Tuesday, October 21, 2014"
output: html_document
---

Data source
-----------
This dataset is derived from the "Human Activity Recognition Using Smartphones Data Set" which was originally made avaiable here: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Feature Selection 
-----------------
Training and the test sets were merged to create one data set
_____________________________________________________________

* test\X_test.txt, test\y_test.txt, test\subject_test.txt were merged into test data table 
* test\X_train.txt, test\y_train.txt, test\subject_train.txt were merged into train data table

From features.txt list of indices corresponding to variables descriving mean values and standard deviations.
This was done by selecting variables which names contain "mean" or "std" (so meanFreq(): Weighted average of the frequency components to obtain a mean frequency were also selected).

Only the measurements on the mean and standard deviation for each measurement were extracted from both training and test data tables and combined into a single table (also including columns with corresponding subject ids and activity labels).

A second, data set with the average of each variable for each activity and each subject was created. The rows were reodered so that activities performed by each subject are in adjacent rows.  
Each activity label was replaced with corresponding activity name from activity_labels.txt.


Column names:
_____________

1. Subject: 
.. range of values [1:30]
.. id of a subject performing ther activity
2. Activity:
.. Name of activity performed

Rest of the colunms corespond to avereaged variables describing mean/std measurements. 
E.g. tGravityAcc-mean()-X
tGravityAcc-mean()-Y
tGravityAcc-mean()-Z
tGravityAcc-std()-X
tGravityAcc-std()-Y
tGravityAcc-std()-Z

Names of these variables are same as in features.txt but the values are averages of each variable for each activity and each subject.
