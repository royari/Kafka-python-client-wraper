# Confluent Kafka Python Client Wrapper for Python

This is a lightweight Python library which lets you push and
execute jobs asynchronously using [Apache Kafka](https://kafka.apache.org/). \
It uses
[confluent-kafka-python](https://docs.confluent.io/platform/current/clients/confluent-kafka-python/html/index.html) under the hood.

## Requirements

* [Apache Kafka](https://kafka.apache.org) 3.4.0
* Python 3.10+

## Getting Started

Start your Kafka instance. 

```shell
docker run -p 9092:9092 <fix this>
```


Start the buffer. This will connect to the KafkaProducer client:

```shell
python confluent_kafka_producer_flask.py
```

Start the workers in separate terminal. This will connect to the KafkaProducer client. The worker executes the job in the background:

```shell
python confluent_consumer.py
[INFO] Starting Worker(hosts=127.0.0.1:9092 topic=page-views, group=group) ...
```

To create a consumer group, running multiple consumer instances that will execute subset of jobs, we need to increase the number of partitions. Following is example command that increases number of partitions to 3 of the page-views Kafka topic.

```shell
 bin/kafka-topics.sh --bootstrap-server localhost:9092 --alter --topic page-views --partitions 3
 ```
 
 ## Demo
 

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/gzsFujHQkUU/0.jpg)](https://youtu.be/gzsFujHQkUU)


```
