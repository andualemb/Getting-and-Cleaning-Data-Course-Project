# Introduction

The script `run_analysis.R`performs 5 of the tasks described in the course project's definition.

* Files having the same number of columns and referring to the same entities are merged together rusing  `rbind()` function.
* Columns with mean and standard deviation measures are extracted from the whole dataset and the colomns are renamed as per the names taken from `features.txt`.
* As activity data is addressed with values 1:6, we take the activity names and IDs from `activity_labels.txt` and they are substituted in the dataset.
* On the whole dataset, those columns with vague column names are corrected.
* Generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is named `averages_data.txt`, and uploaded to this repository.

# Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` extracted data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the datasets to further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_and_std_features`, a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` into one dataset.
* `averages_data` contains the relevant averages which will be saved as a text file. 
* `ddply()` from the plyr package is used to apply `colMeans()`.
