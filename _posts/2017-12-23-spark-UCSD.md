---
layout: post
title: Some MongoDB/Spark exercises (part 2)
---
This is an assignment in Coursera Big Data course by UCSD.

Part 1 is about MongoDB and Par 2 is about simple analysis with Spark tools.

This hands on is based on Cloudera Quickstart VM.

So we'll read in country list and tweet list first, joint the two dataframes and try to answer given questions.

### Read country list from csv file and create dataframe.  
Data will be read to RDD first and then converted to dataframe. After Spark 2.1, we can read csv to dataframe in one shot using "spark.read".  
![country-list](/images/ucsd-mongodb/country-list.png)

### Read tweet data from csv file exported from part 1.
![tweet-list](/images/ucsd-mongodb/tweet-list.png)
We did removal of empty lines so we can see the lines number changed.  

### Next do a word count to tweet data
![tweet-map](/images/ucsd-mongodb/tweet-map.png)
So we can see after flatMap, line number changed from 13396 to 231695 which reflected flatMap this transformation has mapped each line in tweetLinesRDDClean to multiple lines with one word each in tweetWords. 

After that, we did a map to convert word lines to tuple lines which kept the same number of lines - 231695. 

And next reduceByKey merged the line with same words to one line so the total line number changed to 55736.  

We can also save this word count result to file and take a look - try a search of France:  
![France](/images/ucsd-mongodb/France.png)  

Hmm...We can see "#France", "France," etc. are treated as different words with their own counts. This is not what we want. We may need to remove punctuation from tweets before counting. But we'll leave it here for now.   

### Next, we'll create dataframe from tweet word count results
![tweet-df](/images/ucsd-mongodb/tweet-df.png)


### So it's time to merge the two dataframe on country name and word columns.
![merge-df](/images/ucsd-mongodb/merge-df.png)

### Finally, let's try to answer some questions.
![questions](/images/ucsd-mongodb/questions.png)  

