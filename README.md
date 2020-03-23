# Hadoop
### Data Storage

After data ingestion, the next step is to store the extracted data. The data either be stored in HDFS or NoSQL database (i.e. HBase). The HDFS storage works well for sequential access whereas HBase for random read/write access.

### Data Processing

The final step in deploying a big data solution is the data processing. The data is processed through one of the processing frameworks like Spark, MapReduce, Pig, etc.

### What is fsck?
fsck stands for File System Check. It is a command used by HDFS. This command is used to check inconsistencies and if there is any problem in the file. For example, if there are any missing blocks for a file, HDFS gets notified through this command.

# Hive 
it look likes a SQL language for generating MapRedicue Code

```
Put files into HDFS:
$ hadoop fs –put *site.xml /u01/bigdatasql_config/bigdatalite
Copy a file from local file system to a directory in HDFS
$ hadoop fs -copyFromLocal A.text Hadoop_Dci/A.txt
```

# Spark
## This repository is going to update based on my challenges in installing and using the Spark
#### Usful link for installing (https://www.youtube.com/watch?v=PbIzjViybM0)




# Kafka
#### Usful link to Install Kafka (https://www.youtube.com/watch?v=TTsOoQ6_QB0)
Kafka is a distributed messaging system providing fast, highly scalable and redundant messaging through a pub-sub model. A consumer pulls messages off of a Kafka topic while producers push messages into a Kafka topic. Lastly, Kafka, as a distributed system, runs in a cluster. Each node in the cluster is called a Kafka broker. Kafka topics are divided into a number of partitions. Partitions allow you to parallelize a topic by splitting the data in a particular topic across multiple brokers. each partition can be placed on a separate machine to allow for multiple consumers to read from a topic in parallel. Each message within a partition has an identifier called its offset. 
#### CMD commands to run and test the Kafka
```
 zookeeper-shell.bat localhost:2181 ls /brokers/ids
 kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic test
 kafka-console-producer.bat --broker-list localhost:9092 --topic test
 kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning
 # localhost:9092 is Kafka Address
 # if we open two CMD windows and run the Producer and Consumer comand in each of them we can see wen a data put to producer the consumer shows it by a delay
 kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning --property print.timestamp=true --partition 0
 kafka-topics.bat --bootstrap-server localhost:9092 --describe
 
 # output:
 Topic: test     PartitionCount: 1       ReplicationFactor: 1    Configs: min.insync.replicas=1,segment.bytes=1073741824
        Topic: test     Partition: 0    Leader: 0       Replicas: 0     Isr: 0
Topic: __consumer_offsets       PartitionCount: 1       ReplicationFactor: 1    Configs: compression.type=producer,min.insync.replicas=1,cleanup.policy=compact,segment.bytes=104857600
        Topic: __consumer_offsets       Partition: 0    Leader: 0       Replicas: 0     Isr: 0
 
```
![Kafka0](https://github.com/m-r-tanha/Spark/blob/master/kafka0.png)

# HBase
#### Summary Hbase Logical Model
Row: Keys lexicographically sorted byte
Cell: 
 - Columns name are byte[]
 - Values are byte[]
 ACID guarantees per row for HBase reads and writes
#### Physical DataModel
![hbase](https://github.com/m-r-tanha/Hadoop-Ecosystem/blob/master/phys%20hbase.png)
