FROM openjdk:11-slim

WORKDIR /kafka

# Get Kafka
RUN apt-get update -qq && apt-get install wget -y -qq && \
    wget --quiet https://dlcdn.apache.org/kafka/3.0.0/kafka_2.12-3.0.0.tgz && \
    tar -zxf kafka_2.12-3.0.0.tgz && \
    cd kafka_2.12-3.0.0

# Make directory for storing log
RUN mkdir -p /data

# Copy script to run Kafka
COPY run-kafka.sh .

# 9092: Default port for Kafka
EXPOSE 9092

# Kafka Broker Server Start
CMD [ "./run-kafka.sh" ]