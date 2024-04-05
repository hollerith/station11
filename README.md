# SIEMMORE

deit station11_kafka_1 kafka-topics --create --topic syslog --partitions 1 --replication-factor 1 --bootstrap-server localhost:9092
deit station11_kafka_1 kafka-topics --create --topic auth --partitions 1 --replication-factor 1 --bootstrap-server localhost:9092

curl -X POST -H "Content-Type: application/json" --data '@syslog_connector_config.json' http://localhost:8083/connectors
curl -X POST -H "Content-Type: application/json" --data '@auth_log_connector_config.json' http://localhost:8083/connectors

curl -X GET http://localhost:8083/connectors

deit station11_kafka_1 kafka-console-consumer --bootstrap-server localhost:9092 --topic syslog --from-beginning --max-messages 10
