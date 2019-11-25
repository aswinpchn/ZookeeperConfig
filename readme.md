# Readme

1. This is boiler-plate code for Zookeeper config. (It written in java)
2. In this we start zookeeper, then one/many broker's' and create topics(With replication factors and partition sizes).
3. We can use this set-up to run zookeeper, We can also download setup from Apache kafka download site, it is the same. (<https://dzone.com/articles/installing-and-running-kafka-on-an-aws-instance).>
4. This setup is prone to many error and needs extensive debugging, google is your friend.
5. The common things that will go wrong is topic errors, deleting them will solve the issues.
6. how and what to delete 
-> Check in (from dataDir in config/zookeper.properties) and (from log.dirs in config/server.properties).
Commonly the commands are <rm -rf F:......logs> and rm -rf /tmp/zookeeper
7. In the scenario below, user topic is produced by node backend and consumed by put to kafka, and then consumed by Kafka Backend.
  And response topic is produced by Kafka backend and put to kafka and then consumed by Node backend.
  ![Alt text](images/KafkaWorkingFullAtchitechture.png?raw=true "Title")
8. To descibe a topic of how it is existing.
```
  bin/kafka-topics.sh --describe --zookeeper localhost:2181 --topic topic_name
```
9. Read this page to know more about kafka zookeeper mgmt and also about kafka. It has good materials.
  (https://kafka.apache.org/quickstart)
