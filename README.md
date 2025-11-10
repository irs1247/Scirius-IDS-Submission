# Scirius IDS Platform – Docker Deployment

## Overview
This project represents a lab deployment of the **Scirius Security Platform**, integrating key components for intrusion detection, log forwarding, and visualization using Docker Compose.

### Architecture
```mermaid
graph TD
    A[Suricata IDS] -->|EVE JSON Logs| B[Fluentd]
    B --> C[Elasticsearch / OpenSearch]
    C --> D[EveBox]
    C --> E[Kibana]
    E --> F[Scirius Web UI]
    D --> F
    G[RabbitMQ] --> H[Celery Worker]
    H --> F
