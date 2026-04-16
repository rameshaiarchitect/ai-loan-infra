# Infra

Local infrastructure setup using Docker for the AI Loan Processing
System.

------------------------------------------------------------------------

## Includes

-   Kafka (Event streaming platform)
-   Zookeeper (Kafka coordination)
-   Postgres (Data persistence)
-   Redis (Caching / future use)

------------------------------------------------------------------------

## Purpose

This setup provides all required services to run the system locally:

-   Kafka for event-driven communication between services
-   Postgres for storing loan and decision data (future use)
-   Redis for caching / performance optimization (future use)

------------------------------------------------------------------------

## How to Run

``` bash
docker compose up -d
```

------------------------------------------------------------------------

## Verify Services

``` bash
docker ps
```

Expected containers:

-   ai-loan-infra-kafka-1
-   ai-loan-infra-zookeeper-1
-   ai-loan-infra-postgres-1
-   ai-loan-infra-redis-1

------------------------------------------------------------------------

## Kafka Configuration

-   External access: localhost:9092 (used by local services)
-   Internal access: ai-loan-infra-kafka-1:29092 (used within Docker
    network)

------------------------------------------------------------------------

## Topics

-   loan.application.submitted

------------------------------------------------------------------------

## Notes

-   Single broker setup for local development
-   KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR is set to 1
-   Topic auto-creation is enabled

------------------------------------------------------------------------

## Reset Environment

``` bash
docker compose down -v
docker compose up -d
```

This removes all volumes and restarts the environment cleanly.
