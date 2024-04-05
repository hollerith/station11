deit station11_kafka_1 kafka-topics --create --topic syslog --partitions 1 --replication-factor 1 --bootstrap-server localhost:9092
deit station11_kafka_1 kafka-topics --create --topic auth --partitions 1 --replication-factor 1 --bootstrap-server localhost:9092
