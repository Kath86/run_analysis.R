## run_analysis.R for Coursera MOOC Getting and Cleaning Data

### Where the raw data is from:

"The data for this project is from the course website represent data collected from the accelerometers form the Samsung Galaxy S Smartphone. The experiments have been carried out with a group of 30 volunteers whithin an age bracket of 19-48 years. Each person performed six activities (WALKING; WALKING_UPSTAIRS; WALKING_DOWNSTRAIRS; SITTING; STANDING; LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist." You can find a full description at the site where the data was obtained: 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

You can find the data for this project here:
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 


### What the script "run_analysis.R" does:

* Step 1 - the script download the data and unzip it by using download.file() and unzip().
* Step 2 - the script is reading the data sets into R via read.file().
* Step 3 - here the script joins both test and training data together with their proper labels, subjects and activitiy labels. Therefor the script is clipping the test-Subject and train-Subject together using rbind(). Put the train and test labels together and merge them with activity_labels.In the next line the script combines the x-train and the x-test data in order to be able to put all three data sets together to one big data set using cbind().
* Step 4- For this asignment it is required to extract only the measurements on the mean and standard diviation for each measurement. In order to this, the script is using grep() to search for matches to argument pattern (here mean() and sd()) within each element of a character vector. To get excat matching, the script use Fixed = TRUE. Then the script extract only the relevant columns from the big data set. 
* Step 5 - Create a second, independant tidy data set with the average of each variable for each activity and each subject. Herefor, the script install the reshape2 package to use melt(). After melt() and dcast the data set into x. The resulting data set is written a tidy data set using write.table().
* Step 6 -  the script prints the tidy data set.




* License:
========
Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.
