### Data Set Information:
"The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed
six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung GalaxyS II) 
on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity 
at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been 
randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width 
sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and 
body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational 
force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window
, a vector of features was obtained by calculating variables from the time and frequency domain."

### For each record it is provided:
* Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
* Triaxial Angular velocity from the gyroscope.
* A 561-feature vector with time and frequency domain variables.
* Its activity label.
* An identifier of the subject who carried out the experiment.

### The raw dataset includes the following files:

* 'features.txt': List of all features.
* 'activity_labels.txt': Links the class labels with their activity name.
* 'train/X_train.txt': Training set.
* 'train/y_train.txt': Training labels.
* 'test/X_test.txt': Test set.
* 'test/y_test.txt': Test labels.
The following files are available for the train and test data. Their descriptions are equivalent.
* 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 
* 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 
* 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration.
* 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second.

### Transformations or work that the script performed to clean up the data

* Step 1 - the script download the data and unzip it by using download.file() and unzip().
* Step 2 - the script is reading the raw data sets into R via read.file().
* Step 3 - here the script joins both test and training data together with their proper labels, subjects and activitiy labels. Therefor the script is clipping the test-Subject and train-Subject together using rbind(). Put the train and test labels together and merge them with activity_labels.In the next line the script combines the x-train and the x-test data in order to be able to put all three data sets together to one big data set using cbind().
* Step 4- For this asignment it is required to extract only the measurements on the mean and standard diviation for each measurement. In order to this, the script is using grep() to search for matches to argument pattern (here mean() and sd()) within each element of a character vector. To get excat matching, the script use Fixed = TRUE. Then the script extract only the relevant columns from the big data set. 
* Step 5 - Create a second, independant tidy data set with the average of each variable for each activity and each subject. Herefor, the script install the reshape2 package to use melt(). After melt() and dcast the data set into x. The resulting data set is written a tidy data set using write.table().
* Step 6 -  the script prints the tidy data set.


### Data after Transformation
Subject_all
         1...30
       
label_names
        WALKING_DOWNSTAIRS; wALKING_UPSTAIRS; WALKING; SITTING; LAYING; STANDING

tBodyAcc-mean()-X 
tBodyAcc-mean()-Y 
tBodyAcc-mean()-Z 
tGravityAcc-mean()-X 
tGravityAcc-mean()-Y
tGravityAcc-mean()-Z 
tBodyAccJerk-mean()-X 
tBodyAccJerk-mean()-Y 
tBodyAccJerk-mean()-Z 
tBodyGyro-mean()-X 
tBodyGyro-mean()-Y
tBodyGyro-mean()-Z 
tBodyGyroJerk-mean()-X 
tBodyGyroJerk-mean()-Y 
tBodyGyroJerk-mean()-Z 
tBodyAccMag-mean() 
tGravityAccMag-mean()
tBodyAccJerkMag-mean() 
tBodyGyroMag-mean() 
tBodyGyroJerkMag-mean() 
fBodyAcc-mean()-X 
fBodyAcc-mean()-Y 
fBodyAcc-mean()-Z
fBodyAccJerk-mean()-X 
fBodyAccJerk-mean()-Y 
fBodyAccJerk-mean()-Z 
fBodyGyro-mean()-X 
fBodyGyro-mean()-Y 
fBodyGyro-mean()-Z
fBodyAccMag-mean() 
fBodyBodyAccJerkMag-mean() 
fBodyBodyGyroMag-mean() 
fBodyBodyGyroJerkMag-mean() 
tBodyAcc-std()-X
tBodyAcc-std()-Y 
tBodyAcc-std()-Z 
tGravityAcc-std()-X 
tGravityAcc-std()-Y 
tGravityAcc-std()-Z 
tBodyAccJerk-std()-X
tBodyAccJerk-std()-Y 
tBodyAccJerk-std()-Z 
tBodyGyro-std()-X 
tBodyGyro-std()-Y
tBodyGyroJerk-std()-Y 
tBodyGyroJerk-std()-Z 
tBodyAccMag-std() 
tGravityAccMag-std() 
tBodyAccJerkMag-std() 
tBodyGyroMag-std()
tBodyGyroJerkMag-std() 
fBodyAcc-std()-X 
fBodyAcc-std()-Y
fBodyAcc-std()-Z 
fBodyAccJerk-std()-X 
fBodyAccJerk-std()-Y
fBodyAccJerk-std()-Z 
fBodyGyro-std()-X 
fBodyGyro-std()-Y 
fBodyGyro-std()-Z 
fBodyAccMag-std() 
fBodyBodyAccJerkMag-std()
fBodyBodyGyroMag-std() 
fBodyBodyGyroJerkMag-std()
tBodyGyro-std()-Z 
tBodyGyroJerk-std()-X


