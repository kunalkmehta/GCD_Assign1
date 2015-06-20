As a part of Course project 1 for Getting and Cleaning Data, through Coursera, this codebook contains following information: 

1) Problem Statement
2) Assumptions
3) Process Steps
4) Variable/Column definitions

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

3) Method of creating the data set: The process can be bronken down in 8 parts:

a) Reading the text files and creating the data frames and vectors, and merging the train and test data with the help of rbind operations
b) Selecting the columns, and reading the values of the variables/columns which should be included in the data set, as given in Assumptions, clause (d). There would be 79 coumns selected. 
c) Merging all the data sets to create one complete data set which has all the rows, columns needed in the data. I have used cbind to complete the operation
e) Use melt command within reshape2 package to identify variables and measurements
f) Use dcast command to get the means of all variable values and group them by activity-subject combinations
g) Use merge command to to a "left join" with the data set created at (f) and give activity descriptions
h) Finally create tidydataset.txt file with the help of write.table command while row.names=FALSE

The tidy data set will have 180 rows, since there are 30 subjects, and 6 activities, hence 180 subject-activity combinations.

4) Variable List:

1. Activity Desc : Describing the activity
                   WALKING
                   WALKING UPSTAIRS
                   WALKING DOWNSTAIRS
                   SITTING
                   STANDING
                   LAYING
2. Subject: Subject number for whom the data has been recorded
3. tBodyAcc-mean()-X
4. tBodyAcc-mean()-Y
5. tBodyAcc-mean()-Z
6. tBodyAcc-std()-X
7. tBodyAcc-std()-Y
8. tBodyAcc-std()-Z
9. tGravityAcc-mean()-X
10. tGravityAcc-mean()-Y
11. tGravityAcc-mean()-Z
12. tGravityAcc-std()-X
13. tGravityAcc-std()-Y
14. tGravityAcc-std()-Z
15. tBodyAccJerk-mean()-X
16. tBodyAccJerk-mean()-Y
17. tBodyAccJerk-mean()-Z
18. tBodyAccJerk-std()-X
19. tBodyAccJerk-std()-Y
20. tBodyAccJerk-std()-Z
21. tBodyGyro-mean()-X
22. tBodyGyro-mean()-Y
23. tBodyGyro-mean()-Z
24. tBodyGyro-std()-X
25. tBodyGyro-std()-Y
26. tBodyGyro-std()-Z
27. tBodyGyroJerk-mean()-X
28. tBodyGyroJerk-mean()-Y
29. tBodyGyroJerk-mean()-Z
30. tBodyGyroJerk-std()-X
31. tBodyGyroJerk-std()-Y
32. tBodyGyroJerk-std()-Z
33. tBodyAccMag-mean()
34. tBodyAccMag-std()
35. tGravityAccMag-mean()
36. tGravityAccMag-std()
37. tBodyAccJerkMag-mean()
38. tBodyAccJerkMag-std()
39. tBodyGyroMag-mean()
40. tBodyGyroMag-std()
41. tBodyGyroJerkMag-mean()
42. tBodyGyroJerkMag-std()
43. fBodyAcc-mean()-X
44. fBodyAcc-mean()-Y
45. fBodyAcc-mean()-Z
46. fBodyAcc-std()-X
47. fBodyAcc-std()-Y
48. fBodyAcc-std()-Z
49. fBodyAcc-meanFreq()-X
50. fBodyAcc-meanFreq()-Y
51. fBodyAcc-meanFreq()-Z
52. fBodyAccJerk-mean()-X
53. fBodyAccJerk-mean()-Y
54. fBodyAccJerk-mean()-Z
55. fBodyAccJerk-std()-X
56. fBodyAccJerk-std()-Y
57. fBodyAccJerk-std()-Z
58. BodyAccJerk-meanFreq()-X
59. fBodyAccJerk-meanFreq()-Y
60. fBodyAccJerk-meanFreq()-Z
61. fBodyGyro-mean()-X
62. fBodyGyro-mean()-Y
63. fBodyGyro-mean()-Z
64. fBodyGyro-std()-X
65. fBodyGyro-std()-Y
66. fBodyGyro-std()-Z
67. fBodyGyro-meanFreq()-X
68. fBodyGyro-meanFreq()-Y
69. fBodyGyro-meanFreq()-Z
70. fBodyAccMag-mean()
71. fBodyAccMag-std()
72. fBodyAccMag-meanFreq()
73. fBodyBodyAccJerkMag-mean()
74. fBodyBodyAccJerkMag-std()
75. fBodyBodyAccJerkMag-meanFreq()
76. fBodyBodyGyroMag-mean()
77. fBodyBodyGyroMag-std()
78. fBodyBodyGyroMag-meanFreq()
79. fBodyBodyGyroJerkMag-mean()
80. fBodyBodyGyroJerkMag-std()
81. fBodyBodyGyroJerkMag-meanFreq()

End of codebook.md

