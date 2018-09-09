#### Jave sample code for Kafka Producer/Consumer



### Example dummy set up for zookeeper and kafka broker



### Config of zookeeper
cat conf/zoo.cfg

### Config of kafka broker
cat config/server.properties

### Start the zookeeper server
bin/zkServer.sh start

bin/zkServer.sh stop

### Start the zookeeper server CLI
bin/zkCli.sh

### Start the kafka broker
bin/kafka-server-start.sh config/server.properties &
bin/kafka-server-start.sh config/server-1.properties &
bin/kafka-server-start.sh config/server-2.properties &

bin/kafka-server-stop.sh config/server.properties 
bin/kafka-server-stop.sh config/server-1.properties 
bin/kafka-server-stop.sh config/server-2.properties 


### Start Kafka producer
192:kafka_2.11-0.9.0.0 Leo$ bin/kafka-console-producer.sh --broker-list localhost:9092 --topic my-replicated-topic 
my test message 1
my test message 2
my test message 3


### Start Kafka consumer to receiver message
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --from-beginning --topic my-replicated-topic --zookeeper localhost:2181

