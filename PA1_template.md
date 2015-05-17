# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

First of all we clean the workspace as you can read on https://support.rstudio.com/hc/en-us/articles/200711843-Working-Directories-and-Workspaces and unzip the data file, which create a ```activity.csv``` file. If ```activity.csv``` exists it will be overwritten.

The scripts stops if no file ```activity.zip``` was found in working directory or it couldn't be unzipped.




```r
rm(list = ls())
zipfile <- "activity.zip"
if (!file.exists(zipfile)) {
    stop ("No activity.zip zipped data file found on working directory")
}
tryCatch({
    unzip("activity.zip", overwrite = TRUE)
}, warning = function(war) {
    stop("Some warnings occur extracting file. Process has stopped.")
}, error = function(err) {
    stop("Error unzipping data file. Process has stopped.")
})
```

Once we have tha CSV file, we import its data into activity data.frame.


```r
activity <- read.csv("activity.csv")
```


## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
