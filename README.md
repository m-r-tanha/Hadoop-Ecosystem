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

```
