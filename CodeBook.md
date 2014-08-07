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
        A sequential unique number allocated for each volunteer who participated in the experiment
         1...30 Suject number
       
label_names             character
        Each subject performed six types of activities, this variable refers to the activity names
            WALKING_DOWNSTAIRS 
            WALKING_UPSTAIRS 
            WALKING
            SITTING 
            LAYING
            STANDING

tBodyAcc-mean()-X           numeric
        Average of all mean readings for time domain body acceleration signals (prefix 't' to denote time and Acc for acceleration) in the X direction
                            -1..1

tBodyAcc-mean()-Y           numeric
        Average of all mean readings for time domain body acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Y direction
                            -1..1

tBodyAcc-mean()-Z           numeric
        Average of all mean readings for time domain body acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Z direction
                            -1..1

tBodyAcc-std()-X            numeric
        Average of all standard deviation readings for time domain body acceleration signals (prefix 't' to denote time and Acc for acceleration) in the X direction
                            -1..1

tBodyAcc-std()-Y            numeric
        Average of all standard deviation readings for time domain body acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Y direction
                            -1..1
  
tBodyAcc-std()-Z            numeric
        Average of all standard deviation readings for time domain body acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Z direction
                            -1..1

tGravityAcc-mean()-X        numeric
        Average of all mean readings for time domain gravity acceleration signals (prefix 't' to denote time and Acc for acceleration) in the X direction
                            -1..1

tGravityAcc-mean()-Y        numeric
        Average of all mean readings for time domain gravity acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Y direction
                            -1..1

tGravityAcc-mean()-Z        numeric
        Average of all mean readings for time domain gravity acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Z direction
                            -1..1

tGravityAcc-std()-X         numeric
        Average of all standard deviation readings for time domain gravity acceleration signals (prefix 't' to denote time and Acc for acceleration) in the X direction
                            -1..1

tGravityAcc-std()-Y         numeric
        Average of all standard deviation readings for time domain gravity acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Y direction
                            -1..1

tGravityAcc-std()-Z         numeric
        Average of all standard deviation readings for time domain gravity acceleration signals (prefix 't' to denote time and Acc for acceleration) in the Z direction
                            -1..1

tBodyAccJerk-mean()-X       numeric
        Average of all mean readings for body linear acceleration derived in time to obtain jerk signals (prefix 't' to denote time and Acc for acceleration) in the X direction
                            -1..1

tBodyAccJerk-mean()-Y       numeric
        Average of all mean readings for body linear acceleration derived in time to obtain jerk signals (prefix 't' to denote time and Acc for acceleration) in the Y direction
                            -1..1

tBodyAccJerk-mean()-Z       numeric
        Average of all mean readings for body linear acceleration derived in time to obtain jerk signals (prefix 't' to denote time and Acc for acceleration) in the Z direction
                            -1..1

tBodyAccJerk-std()-X        numeric
        Average of all standard deviation readings for body linear acceleration derived in time to obtain jerk signals (prefix 't' to denote time and Acc for acceleration) in the X direction
                            -1..1

tBodyAccJerk-std()-Y        numeric
        Average of all standard deviation readings for body linear acceleration derived in time to obtain jerk signals (prefix 't' to denote time and Acc for acceleration) in the Y direction
                            -1..1

tBodyAccJerk-std()-Z        numeric
        Average of all standard deviation readings for body linear acceleration derived in time to obtain jerk signals (prefix 't' to denote time and Acc for acceleration) in the Z direction
                            -1..1

tBodyGyro-mean()-X          numeric
        Average of all mean readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the X direction
                            -1..1

tBodyGyro-mean()-Y          numeric
        Average of all mean readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Y direction
                            -1..1

tBodyGyro-mean()-Z          numeric
        Average of all mean readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Z direction
                            -1..1

tBodyGyro-std()-X           numeric
        Average of all standard deviation readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the X direction
                            -1..1

tBodyGyro-std()-Y           numeric
        Average of all standard deviation readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Y direction
                            -1..1

tBodyGyro-std()-Z           numeric
        Average of all standard deviation readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Z direction
                            -1..1

tBodyGyroJerk-mean()-X      numeric
        Average of all mean readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the X direction
                            -1..1

tBodyGyroJerk-mean()-Y      numeric
        Average of all mean readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Y direction
                            -1..1

tBodyGyroJerk-mean()-Z      numeric
        Average of all mean readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Z direction
                            -1..1

tBodyGyroJerk-std()-X       numeric
        Average of all standard deviation readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the X direction
                            -1..1

tBodyGyroJerk-std()-Y       numeric
        Average of all standard deviation readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Y direction
                            -1..1

tBodyGyroJerk-std()-Z       numeric
        Average of all standard deviation readings for body angular velocity derived in time to obtain jerk signals (prefix 't' to denote time and Gyro for angular velocity) in the Z direction
                            -1..1

tBodyAccMag-mean()          numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

tBodyAccMag-std()           numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

tGravityAccMag-mean()       numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

tGravityAccMag-std()        numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

tBodyAccJerkMag-mean()      numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

tBodyAccJerkMag-std()       numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

tBodyGyroMag-mean()         numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

tBodyGyroMag-std()          numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

tBodyGyroJerkMag-mean()      numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1
  
tBodyGyroJerkMag-std()      numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyAcc-mean()-X           numeric
        Average of all mean readings for body acceleration signals by applying Fast Fourier Transform(FFT)(prefix 'f' to denote FFT and Acc for acceleration) in the X direction
                            -1..1

fBodyAcc-mean()-Y           numeric
        Average of all mean readings for body acceleration signals by applying Fast Fourier Transform(FFT)(prefix 'f' to denote FFT and Acc for acceleration) in the Y direction
                            -1..1

fBodyAcc-mean()-Z           numeric
        Average of all mean readings for body acceleration signals by applying Fast Fourier Transform(FFT)(prefix 'f' to denote FFT and Acc for acceleration) in the Z direction
                            -1..1

fBodyAcc-std()-X            numeric
        Average of all standard deviation readings for body acceleration signals by applying Fast Fourier Transform(FFT)(prefix 'f' to denote FFT and Acc for acceleration) in the X direction
                            -1..1

fBodyAcc-std()-Y            numeric
        Average of all standard deviation readings for body acceleration signals by applying Fast Fourier Transform(FFT)(prefix 'f' to denote FFT and Acc for acceleration) in the Y direction
                            -1..1

fBodyAcc-std()-Z            numeric
        Average of all standard deviation readings for body acceleration signals by applying Fast Fourier Transform(FFT)(prefix 'f' to denote FFT and Acc for acceleration) in the Z direction
                            -1..1

fBodyAccJerk-mean()-X       numeric
        Average of all mean readings for body linear acceleration derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Acc for acceleration) in the X direction
                            -1..1

fBodyAccJerk-mean()-Y       numeric
        Average of all mean readings for body linear acceleration derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Acc for acceleration) in the Y direction
                            -1..1

fBodyAccJerk-mean()-Z       numeric
        Average of all mean readings for body linear acceleration derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Acc for acceleration) in the Z direction
                            -1..1

fBodyAccJerk-std()-X        numeric
        Average of all standard deviation readings for body linear acceleration derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Acc for acceleration) in the X direction
                            -1..1

fBodyAccJerk-std()-Y        numeric
        Average of all standard deviation readings for body linear acceleration derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Acc for acceleration) in the Y direction
                            -1..1

fBodyAccJerk-std()-Z        numeric
        Average of all standard deviation readings for body linear acceleration derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Acc for acceleration) in the Z direction
                            -1..1

fBodyGyro-mean()-X          numeric
        Average of all mean readings for body angular velocity derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Gyro for angular velocity) in the X direction
                            -1..1

fBodyGyro-mean()-Y          numeric
        Average of all mean readings for body angular velocity derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Gyro for angular velocity) in the Y direction
                            -1..1

fBodyGyro-mean()-Z          numeric
        Average of all mean readings for body angular velocity derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Gyro for angular velocity) in the Z direction
                            -1..1

fBodyGyro-std()-X           numeric
        Average of all standard deviation readings for body angular velocity derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Gyro for angular velocity) in the X direction
                            -1..1

fBodyGyro-std()-Y           numeric
        Average of all standard deviation readings for body angular velocity derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Gyro for angular velocity) in the Y direction
                            -1..1

fBodyGyro-std()-Z           numeric
        Average of all standard deviation readings for body angular velocity derived by applying Fast Fourier Transform(FFT) to obtain jerk signals (prefix 'f' to denote FFT and Gyro for angular velocity) in the Z direction
                            -1..1

fBodyAccMag-mean()          numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyAccMag-std()           numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyBodyAccJerkMag-mean()  numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyBodyAccJerkMag-std()   numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyBodyGyroMag-mean()     numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyBodyGyroMag-std()      numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1

fBodyBodyGyroJerkMag-mean() numeric
        Average of all mean readings for the magnitude calculated using the Euclidean norm
                            -1..1
 
fBodyBodyGyroJerkMag-std()  numeric
        Average of all standard deviation readings for the magnitude calculated using the Euclidean norm
                            -1..1


