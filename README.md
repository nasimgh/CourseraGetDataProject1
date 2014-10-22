---
title: "README"
author: "Nasim"
date: "Tuesday, October 21, 2014"
output: html_document
---
Coursera
_____________________

Getting and Cleaning Data Course Project

### run_analysis.R

Script does the following: 

* Extract only the measurements on the mean and standard deviation for each measurement
  
    ```R
    means_and_std_colnames<-colnames(X_test)[indices]
    X_test_subset<-cbind(subject_test,y_test,subset(X_test,select=means_and_std_colnames))
    X_train_subset<-cbind(subject_train,y_train,subset(X_train,select=means_and_std_colnames))
    ```
    
* Merge the training and the test sets to create one data set.
    ```R
    Xy<-rbind(X_test_subset, X_train_subset)
    ```

* Uses descriptive activity names to name the activities in the data set
    ```R
    tidy$Activity<-activity_labels[tidy$Activity,]
    ```

* Appropriately labels the data set with descriptive activity names. 
* Creates a second, independent tidy data set with the average of each variable for each activity and each subject.
    ```R    
    tidy<-aggregate(Xy[,3:ncol(Xy)],list(Subject=Xy$subjects, Activity=Xy$labels), mean)
    tidy<-tidy[order(tidy$Subject),]
    ```
