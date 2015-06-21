Thank you so much for taking your time out to read this, I know reading a README can be pretty boring and not to 
mention, "useless". But I believe it can be the best place to understand what to expect, especially if you are about to look 
into someone else's code, or may be trying to evaluate it ;)

Anyways, this detailed explanation about the code, process, problem statement, assumptions etc is given in codebook.md. Please read this before you see the code. 

Explanation of the code and the steps is also given in the run_analysis.R in comments. 

I had a lot of fun creating this assignment, hpe you won't find it funny while evaluating it :)

Cheers, and best of luck. 

################################################################################################################################
As a part of Course project 1 for Getting and Cleaning Data, through Coursera, this codebook contains following information:

1) Problem Statement 2) Assumptions 3) Process Steps 4) Variable/Column definitions

Everything over here describes the process and methods utilized to create the tidy data set, but for the code you will have to refer to run_analysis.R, part of this repo.

1) Problem Statement: We needed to create a code by the name of run_analysis.R, which does the following:

a) Merges the training and the test sets to create one data set. b) Extracts only the measurements on the mean and standard deviation for each measurement. c) Uses descriptive activity names to name the activities in the data set d) Appropriately labels the data set with descriptive variable names. e) From the data set in step d, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

2) I have taken the following assumptions to create the code:

a) The dataset, unzipped dataset, that we downloaded from the Coursera website, is kept in the working directory in as-is format and path b) The dataset is in .txt format, with common space delimiter, " " c) We need to merge the datasets given in Test and Train folders to create the data set d) In problem statement, clause (b), we need to extract the variable/column values of the mean and standard deviasion measurements. I am identifying these measurements with the name "mean" or "std" within the column names e) Column names are given in features.txt file within the data downloaded f) I am going to use same column names as "descriptive" column names listed in problem statement, clause (d) g) For problem statement, clause (c), name of the activities are given in activity_labels.txt file within the downloaded data h) Final tidy data set should comply with the principles of tidy data set, which means that for each subject-activity combination, we should be having exactly one row, giving the mean (or average) of the each column values. i) Last and MOST IMPORTANT OF ALL, you would be kind while evaluating this exercise :)

3) Method of creating the data set: The process can be bronken down in 8 parts:

a) Reading the text files and creating the data frames and vectors, and merging the train and test data with the help of rbind operations b) Selecting the columns, and reading the values of the variables/columns which should be included in the data set, as given in Assumptions, clause (d). There would be 79 coumns selected. c) Merging all the data sets to create one complete data set which has all the rows, columns needed in the data. I have used cbind to complete the operation e) Use melt command within reshape2 package to identify variables and measurements f) Use dcast command to get the means of all variable values and group them by activity-subject combinations g) Use merge command to to a "left join" with the data set created at (f) and give activity descriptions h) Finally create tidydataset.txt file with the help of write.table command while row.names=FALSE

The tidy data set will have 180 rows, since there are 30 subjects, and 6 activities, hence 180 subject-activity combinations.

4) Variable List:

Activity Desc : Describing the activity WALKING WALKING UPSTAIRS WALKING DOWNSTAIRS SITTING STANDING LAYING
Subject: Subject number for whom the data has been recorded
tBodyAcc-mean()-X
tBodyAcc-mean()-Y
tBodyAcc-mean()-Z
tBodyAcc-std()-X
tBodyAcc-std()-Y
tBodyAcc-std()-Z
tGravityAcc-mean()-X
tGravityAcc-mean()-Y
tGravityAcc-mean()-Z
tGravityAcc-std()-X
tGravityAcc-std()-Y
tGravityAcc-std()-Z
tBodyAccJerk-mean()-X
tBodyAccJerk-mean()-Y
tBodyAccJerk-mean()-Z
tBodyAccJerk-std()-X
tBodyAccJerk-std()-Y
tBodyAccJerk-std()-Z
tBodyGyro-mean()-X
tBodyGyro-mean()-Y
tBodyGyro-mean()-Z
tBodyGyro-std()-X
tBodyGyro-std()-Y
tBodyGyro-std()-Z
tBodyGyroJerk-mean()-X
tBodyGyroJerk-mean()-Y
tBodyGyroJerk-mean()-Z
tBodyGyroJerk-std()-X
tBodyGyroJerk-std()-Y
tBodyGyroJerk-std()-Z
tBodyAccMag-mean()
tBodyAccMag-std()
tGravityAccMag-mean()
tGravityAccMag-std()
tBodyAccJerkMag-mean()
tBodyAccJerkMag-std()
tBodyGyroMag-mean()
tBodyGyroMag-std()
tBodyGyroJerkMag-mean()
tBodyGyroJerkMag-std()
fBodyAcc-mean()-X
fBodyAcc-mean()-Y
fBodyAcc-mean()-Z
fBodyAcc-std()-X
fBodyAcc-std()-Y
fBodyAcc-std()-Z
fBodyAcc-meanFreq()-X
fBodyAcc-meanFreq()-Y
fBodyAcc-meanFreq()-Z
fBodyAccJerk-mean()-X
fBodyAccJerk-mean()-Y
fBodyAccJerk-mean()-Z
fBodyAccJerk-std()-X
fBodyAccJerk-std()-Y
fBodyAccJerk-std()-Z
BodyAccJerk-meanFreq()-X
fBodyAccJerk-meanFreq()-Y
fBodyAccJerk-meanFreq()-Z
fBodyGyro-mean()-X
fBodyGyro-mean()-Y
fBodyGyro-mean()-Z
fBodyGyro-std()-X
fBodyGyro-std()-Y
fBodyGyro-std()-Z
fBodyGyro-meanFreq()-X
fBodyGyro-meanFreq()-Y
fBodyGyro-meanFreq()-Z
fBodyAccMag-mean()
fBodyAccMag-std()
fBodyAccMag-meanFreq()
fBodyBodyAccJerkMag-mean()
fBodyBodyAccJerkMag-std()
fBodyBodyAccJerkMag-meanFreq()
fBodyBodyGyroMag-mean()
fBodyBodyGyroMag-std()
fBodyBodyGyroMag-meanFreq()
fBodyBodyGyroJerkMag-mean()
fBodyBodyGyroJerkMag-std()
fBodyBodyGyroJerkMag-meanFreq()
#############################################################################################################################
