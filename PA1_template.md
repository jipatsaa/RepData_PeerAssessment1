# Reproducible Research: Peer Assessment 1
## Needed libraries

```r
    library(plyr)
    library(ggplot2)
```
## Loading and preprocessing the data

```r
      unzip("activity.zip")
      data<-read.csv("activity.csv",sep = ",")
      data$date<-as.Date(data$date)
```

## What is mean total number of steps taken per day?`

```r
      dataByDate <- ddply(data, .(date), summarise, meanSteps = mean(steps, na.rm = TRUE))
      ggplot(dataByDate, aes(date, meanSteps))+ ggtitle("Steps by date")+theme(plot.title = element_text(face="bold"))+geom_point()+geom_line()
```

```
## Warning: Removed 8 rows containing missing values (geom_point).
```

```
## Warning: Removed 2 rows containing missing values (geom_path).
```

![](./PA1_template_files/figure-html/unnamed-chunk-3-1.png) 

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
