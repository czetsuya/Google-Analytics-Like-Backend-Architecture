# Google-Analytics-Like-Backend-Architecture

## Solution 1 - Using Apache Druid

1.) Users access a load balance client application that trigger and push events.

2.) Kafka receive the events.

3.) Kafka forward the events to another Kafka node for raw storage.

4.) Spark Streaming subscribe and process messages from Kafka.

5.) Spark Streaming writes to Apache Druid.

6.) A web project powered by React integrates with either Apache Superset or Grafana which pulls the data from Druid to provide enterprise business intelligence.

## Solution 2 - Using Apache Cassandra

1.) Users access a load balance client application that trigger and push events.

2.) Kafka receive the events.

3.) Kafka forward the events to another Kafka node for raw storage.

4.) Spark Streaming subscribe and process messages from Kafka.

5.) Spark Streaming writes to Apache Cassandra.

6.) Spark Batch crunch the data from Cassandra and save to Postgres TimescaleDB which supports time-series queries.

7.) A Spring REST API project is preferred to expose service to access data.

8.) A web project powered by React integrates with either Apache Superset or Grafana which pulls the data from the REST API to provide enterprise business intelligence.
