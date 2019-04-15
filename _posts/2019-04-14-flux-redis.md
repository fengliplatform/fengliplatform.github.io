
It is interesting that we can find flux topology example for HBase and Kafka but it's hard to find one for Redis. 

A HBASE + Storm/Flux example can be found at: https://github.com/apache/storm/blob/master/flux/flux-examples/src/main/resources/simple_hbase.yaml

A Kafka + Storm/Flux example can be found at:
https://docs.microsoft.com/en-us/azure/hdinsight/hdinsight-apache-storm-with-kafka

Let's see how we can do a write to Redis.

So a flux word count example can be found at https://github.com/Azure-Samples/hdinsight-python-storm-wordcount. On top of
that what if we want to save the word count results to Redis?

We just need to add a bolt to receive word count results from count bolt and write them to Redis. We can call this bolt "redis-store-bolt".
Simply it can be defined like following in Flux topology.yaml:

  - id: "redis-store-bolt"
    className: "org.apache.storm.redis.bolt.RedisStoreBolt"
    constructorArgs:
      - ref: "poolConfig"
      - ref: "storeMapper"
    parallelism: 1

Storm has ready-to-use class to talk to Redis - org.apache.storm.redis.bolt.RedisStoreBolt. To initialize this class we need two
parameters: 1) Redis service configuration in the format of class JedisPoolConfig, 2) a RedisStoreMapper object to map incoming
data to be key/value pairs in Redis. 
(See details: https://storm.apache.org/releases/1.1.2/javadocs/org/apache/storm/redis/bolt/RedisStoreBolt.html).

And in "components" section of the topology.yaml file we can define for the two parameters:
  - id: "poolConfig"
    className: "org.apache.storm.redis.common.config.JedisPoolConfig"
    constructorArgs:
      - "localhost"
      - 6379

  - id: "storeMapper"
    className: "org.apache.storm.redis.common.mapper.RedisStoreMapper"
    constructorArgs:
<ToDo>
