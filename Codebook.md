#Code book

The run_analysis.R script performs the data preparation and then followed by the 5 steps required as described in the course project’s definition.

1. Download the dataset
Dataset downloaded and extracted under the folder called UCI HAR Dataset

2. Assign each data to variables
- Read all the files
- Combine them into a dataframe
- Assign each data to variables

3. Merges the training and the test sets to create one data set
data.all <- rbind(data.train, data.test)

4. Extracts only the measurements on the mean and standard deviation for each measurement
mean_std.select <- grep('mean|std', features)
data.sub <- data.all[,c(1,2,mean_std.select + 2)]

5. Uses descriptive activity names to name the activities in the data set
Read the labels from the activity_labels.txt file

6. Appropriately labels the data set with descriptive variable names
All Acc in column’s name replaced by Accelerometer
All Gyro in column’s name replaced by Gyroscope
All Mag in column’s name replaced by Magnitude
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time

7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
data_tidy.txt is created by taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export it into data_tidy.txt file.
