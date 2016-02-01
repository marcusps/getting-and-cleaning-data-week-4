# CodeBook for Week 4 Assignment of "Getting and Cleaning Data" course

## Data set `tidy-summary.txt`

### Format

This data set is provided as a space-separated-value file format. Factors are represented by strings, which are quoted with the double quote character ("). All other varibles are numeric.

### Transformations from original data set

Unziping the [file](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) obtained from [Human Activity Recognition Using Smartphones Data Set 
 (UCI Machine Learning Repository)](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones#), one finds the files 
 
```
test/X_test.txt
test/subject_test.txt
test/y_test.txt
train/X_train.txt
train/subject_train.txt
train/y_train.txt
```

which were all combined into this data set. The main transformations performed were 

   + the translation of the data of `train/subject_train.txt` and `test/subject_test.txt` into factors (to emphasize that ordering of the integers appears to be meaningless)
   
   + the translation of the data of `train/y_train.txt` and `test/y_test.txt` into factors, but following the correspondence document in `activity_labels.txt`, and this `y` variable was renamed `activity`

   + for each `subject` and `activity` pairing, and for each observation of this pairing, only mean and standard deviation of the variables recorded in the observation were kept. In turns, only the averages of these are kept for each given `subject` and `activity`.

   + aside from the `subject` and `activity`, all variables are numeric.

### Variables

Variable names follow the variable names in the UCI data set, except dashes, parentheses, and commas have been removed. Moreover, only mean and standard deviation of each of the recorded observations are kept in the tidy data sets. Thus, from the 563 different variables in the `X_*.txt` data sets, we end up with 81. By combining the information about activity and subject (i.e., all three files within the `test` and `train` data sets), we end 83 different variables. The first two are `activity` and `subject`, both of which are factors. All remaining variables are numeric. 

