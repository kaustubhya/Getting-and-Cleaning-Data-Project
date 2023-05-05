# Getting-and-Cleaning-Data-Project

1. Loads the dplyr library.
2. Sets the filename variable to the name of the zip file to download.
3. Checks if the filename already exists. If not, it downloads it from the given URL using the download.file function.
4. Checks if the folder "UCI HAR Dataset" exists. If not, it extracts the contents of the zip file using the unzip function.
5. Reads in the following data sets as data frames: features.txt, activity_labels.txt, subject_test.txt, X_test.txt, y_test.txt, subject_train.txt, X_train.txt, and y_train.txt. It assigns column names to each data frame using the col.names argument.
6. Merges the subject, code, and X data frames using cbind and rbind functions to create the Merged_Data data frame.
7. Selects only the columns that contain the mean and standard deviation measurements using the select function from the dplyr package. It assigns the resulting data frame to TidyData.
8. Replaces the code column values in TidyData with their corresponding activity names from the activities data frame.
9. Cleans up the variable names in TidyData using multiple gsub functions that replace various abbreviations and patterns with more descriptive names.
10. Calculates the mean of all measurements for each combination of subject and activity using the group_by and summarise_all functions from the dplyr package. It assigns the resulting data frame to FinalData.
11. Writes FinalData to a text file named "FinalData.txt" using the write.table function with row.names=FALSE to exclude row names in the output file.
12. Finally, it displays the structure of FinalData using the str function.
