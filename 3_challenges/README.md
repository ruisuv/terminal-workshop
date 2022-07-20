# Challenges

## Reproduce the issue
Follow the instructions on [README.md](https://github.com/ruisuv/kafka-hello-world-terminal)
```
apt-get install docker
cd /repos/kafka-hello-world-terminal/ 
cd src/main/resources/ 
docker-compose up -d 
cd - 
./mvnw clean install 
java -jar target/*.jar
```

## Make a Request
```
curl -X POST http://localhost:8080/messages \
-H "Content-Type: application/json" \
-d '{"author":"Arturo","text":"First Message"}'
```
