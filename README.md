# Infra

Local infrastructure setup using Docker for the AI Loan Processing System.

## Includes

- Kafka (Event streaming platform)
- Zookeeper (Kafka coordination)
- Postgres (Data persistence)
- Redis (Caching / future use)

---

## Purpose

This setup provides all required services to run the system locally:

- Kafka for event-driven communication between services
- Postgres for storing loan and decision data (future use)
- Redis for caching / performance optimization (future use)

---

## How to Run

```bash
docker compose up -d
