# Challenges

## Reproduce the issue
Follow the instructions on [README.md](https://github.com/ruisuv/kafka-hello-world-terminal)

### Set up the Kafka Server
You can find these instructions on dotfile `.kafka-setup`

```
wget https://dlcdn.apache.org/kafka/3.2.0/kafka_2.12-3.2.0.tgz
mkdir /kafka
mv kafka_2.12-3.2.0.tgz /kafka
/kafka/kafka_2.12-3.2.0/bin/zookeeper-server-start.sh /kafka/kafka_2.12-3.2.0/config/zookeeper.properties &
/kafka/kafka_2.12-3.2.0/bin/kafka-server-start.sh /kafka/kafka_2.12-3.2.0/config/server.properties &
```
### Verify Kafka Server is working
Create a consumer so new messages can be read from here
```
sh /kafka/kafka_2.12-3.2.0/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic messages
```
Try sending message from Kafka Script and then start typing messages
```
sh /kafka/kafka_2.12-3.2.0/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic messages
```



### Reproduce the issue

Build and run the Spring Application
```
cd /repos/kafka-hello-world-terminal/ && ./mvnw clean install && java -jar target/*.jar
```
Try by sending a message
```
curl -X POST http://localhost:8080/messages \
-H "Content-Type: application/json" \
-d '{"author":"Arturo","text":"First Message"}'
```
Application log should state something as following:
> 2022-07-20 18:13:31.420  INFO 2129 --- [nio-8080-exec-2] c.e.k.controller.MessageController       : Arturo sent the message First Message

But consumer logs doesn't show anything