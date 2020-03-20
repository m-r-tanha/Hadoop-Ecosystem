# Spark
## This repository is going to update based on my challenges in installing and using the Spark
#### Usful link for installing (https://www.youtube.com/watch?v=PbIzjViybM0)




# Kafka
#### Usful link to Install Kafka (https://www.youtube.com/watch?v=TTsOoQ6_QB0)
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
