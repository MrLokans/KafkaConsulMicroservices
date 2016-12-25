FROM openjdk:8

# Override for every instance
ARG kafka_broker_id=1

ADD kafka_2.11-0.10.1.1.tgz /

RUN mv /kafka_2.11-0.10.1.1 /kafka && \
    sed -i s/localhost:2181/zookeeper:2181/g /kafka/config/server.properties && \
    sed -i s/broker.id=0/broker.id=${kafka_broker_id}/g /kafka/config/server.properties

EXPOSE 9092