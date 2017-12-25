---
layout: post
title: Some MongoDB/Spark exercises (part 2)
---
This is an assignment in Coursera Big Data course by UCSD.

Part 1 is about MongoDB and Par 2 is about simple analysis with Spark tools.

This hands on is based on Cloudera Quickstart VM.

So we'll read in country list and tweet list first, joint the two dataframes and try to answer given questions.

#### Read country list from csv file and create dataframe.  
Data will be read to RDD first and then converted to dataframe. After Spark 2.1, we can read csv to dataframe in one shot using "spark.read".  
![country-list](/images/ucsd-mongodb/country-list.png)

#### Read tweet data from csv file exported from part 1.
![tweet-list](/images/ucsd-mongodb/tweet-list.png)
We did removal of empty lines so we can see the lines number changed.

#### Next do a word count to tweet data
![tweet-map](/images/ucsd-mongodb/tweet-map.png)

#### 
