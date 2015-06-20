As a part of Course project 1 for Getting and Cleaning Data, through Coursera, this codebook contains following information: 

1) Problem Statement
2) Assumptions
3) Method of creating the data
4) Process Steps
5) Variable/Column definitions

Everything over here describes the process and methods utilized to create the tidy data set, but for the code you will have to refer to run_analysis.R, part of this repo. 

1) Problem Statement: We needed to create a code by the name of run_analysis.R, which does the following:

a) Merges the training and the test sets to create one data set.
b) Extracts only the measurements on the mean and standard deviation for each measurement. 
c) Uses descriptive activity names to name the activities in the data set
d) Appropriately labels the data set with descriptive variable names. 
e) From the data set in step d, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

2) I have taken the following assumptions to create the code: 

a) The dataset, unzipped dataset, that we downloaded from the Coursera website, is kept in the working directory in as-is format and path
b) The dataset is in .txt format, with common space delimiter, " "
c) We need to merge the datasets given in Test and Train folders to create the data set
d) In problem statement, clause (b), we need to extract the variable/column values of the mean and standard deviasion measurements. I am identifying these measurements with the name "mean" or "std" within the column names
e) Column names are given in features.txt file within the data downloaded
f) I am going to use same column names as "descriptive" column names listed in problem statement, clause (d)
g) For problem statement, clause (c), name of the activities are given in activity_labels.txt file within the downloaded data
h) Final tidy data set should comply with the principles of tidy data set, which means that for each subject-activity combination, we should be having exactly one row, giving the mean (or average) of the each column values. 
i) Last and MOST IMPORTANT OF ALL, you would be kind while evaluating this exercise :)

3) Method of creating the data set: 
