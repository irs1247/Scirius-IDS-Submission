# 🛡️ Scirius IDS Platform – Docker Deployment

## 📖 Overview
This repository provides a lab deployment of the **Scirius Security Platform**, built around **Suricata IDS** for real-time network threat detection and analysis.  

The deployment integrates the following key components:
- **Suricata** — Performs intrusion detection and traffic analysis.  
- **Fluentd** — Collects and forwards Suricata EVE JSON logs.  
- **Elasticsearch / OpenSearch** — Stores and indexes alert and event data.  
- **EveBox** — Visualizes Suricata alerts for investigation.  
- **Kibana (OpenSearch Dashboards)** — Provides advanced visualization and analytics.  
- **RabbitMQ** — Message broker for distributed task management.  
- **Celery Workers** — Handles background data processing tasks.  
- **Nginx / Scirius Web UI** — Centralized management interface for rule updates and alert review.  

All components are orchestrated using **Docker Compose**, enabling reproducible, modular setup and easy teardown.

---

## ⚙️ Setup Instructions

1. **Clone this repository**
   ```bash
   git clone https://github.com/irs1247/Scirius-IDS-Submission.git
   cd Scirius-IDS-Submission

🧠 Architecture 
graph TD
A[Suricata IDS] -->|EVE JSON Logs| B[Fluentd]
B --> C[Elasticsearch / OpenSearch]
C --> D[EveBox]
C --> E[Kibana]
E --> F[Scirius Web UI]
D --> F
G[RabbitMQ] --> H[Celery Worker]
H --> F

---

## 🧠 Project Outcome
Successfully deployed and validated the **Scirius IDS Platform** using Docker Compose.  
Most core services (Elasticsearch, RabbitMQ, Fluentd, and Kibana) reached healthy state.  
Encountered and documented issues with Arkime and PostgreSQL containers, as noted in the [WORK_SUMMARY.md](WORK_SUMMARY.md) file.

