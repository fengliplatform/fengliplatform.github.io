---
layout: post
title: Some MongoDB/Spark exercises (part 1)
---
This is an assignment in Coursera Big Data course by UCSD.

Part 1 is about MongoDB and Par 2 is about simple analysis with Spark tools.

This hands on is based on Cloudera Quickstart VM.

### Start MongoDB server
![start MongoDB server](/images/ucsd-mongodb/start-mongodb.png)

### Start MongoDB client and list existing databases
![start MongoDB Client](/images/ucsd-mongodb/start-mongodb-client.png)

### Choose database "sample" and then list collections
![first glance](/images/ucsd-mongodb/first.png)
So we took a look at how may records in collection "users" and showed fields and values of the first record.

### Next, question 1, how many tweets have location not null?
We can use following commands to figure it out.  
![location null](/images/ucsd-mongodb/location.png)

Also another way  
![location null 2](/images/ucsd-mongodb/location2.png)

### Question 2, How many people have more followers than friends?
![followers-friends](/images/ucsd-mongodb/followers-friends.png)

### Question 3, Return text of tweets which have the string "http://" ?
![http](/images/ucsd-mongodb/http.png)

### Question 4, Return all the tweets which contain text "England" but not "UEFA" ?
![england-uefa](/images/ucsd-mongodb/england-uefa.png)

### Question 5, Get all the tweets from the location "Ireland" and contains the string "UEFA" And then find who has most of the friends.  
So we'll create text index and do search with multiple conditions on it.  
![index](/images/ucsd-mongodb/index.png)  
![q5](/images/ucsd-mongodb/q5.png)  

### Last, let's export collection users to csv file and use it in part 2 tasks.  
A field list has to be specified to export to csv file.  
![export](/images/ucsd-mongodb/export.png) 


