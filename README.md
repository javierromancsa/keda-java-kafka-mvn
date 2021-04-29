# keda-java-kafka-mvn

This rebo is build from scarct a maven project for a simple java kafka consumer. Dockerize the build to create an image using Azure Container  

# Steps for running this sample

## Using the maven build the package and jar to deploy your code. 
 - Modifiy src/main/java/jrs/kafka/client/SimpleKafkaConsumer.java on the properties BOOTSTRAP_SERVERS_CONFIG and GROUP_ID_CONFIG with your brokers IPs, hostnames or URL and the consumer group name. See below example :
linkforimage
 - Also modify consumer.subscribe to have the topic you're going to consume. See below example: link
 - 
## execute  mvn clean package -DskipTests

## Test your code is able to consume from the topic you have specify by running the following command
java -jar target/kafka-consumer-1.0-SNAPSHOT.jar

## Build your docker image and push it to your azure container registry using the dockerfile in the repo
az acr build --registry jrsacr --image keda-test:v1 -f dockerfile .

## 
