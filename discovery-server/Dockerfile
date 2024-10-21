FROM openjdk:17


ARG JAR_FILE=target/*.jar

ADD ${JAR_FILE} discovery-service.jar

ENV SERVER_PORT=8761
ENV SERVER_HOST=discovery

ENTRYPOINT java -jar discovery-service.jar \
    --eureka.instance.hostname=localhost \
    --eureka.client.serviceUrl.defaultZone=http://${SERVER_HOST}:8761/eureka \
    server.port=${SERVER_PORT}
EXPOSE ${SERVER_PORT}