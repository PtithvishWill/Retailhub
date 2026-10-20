# RetailHub: Enterprise E-Commerce & Medallion Data Lakehouse Platform

An enterprise-grade, end-to-end e-commerce platform integrated with a real-time behavioral fraud detection engine (**FraudGuard**) and a cloud-native **Medallion Data Lakehouse (Bronze → Silver → Gold)** built with **React**, **Node.js/Express**, **Apache Kafka**, **Apache Spark (PySpark)**, **Apache Airflow**, and **Amazon Web Services (AWS)**.

---

## 🏗️ Platform Architecture

The repository combines two core systems:

```
Retailhub/
├── Webiste/                           # Full-Stack E-Commerce & Telemetry Platform
│   └── RetailHub-E-Commerce-Webiste-main/
│       ├── frontend/                  # React (Vite, TypeScript, Tailwind CSS) SPA
│       ├── backend/                   # Node.js/Express REST API & MySQL
│       ├── kafka/                     # Kafka telemetry producer & event stream
│       └── Documents/                 # Architecture diagrams, specifications & reports
│
└── ETL/                               # Real-Time & Batch Data Lakehouse Platform
    └── Retailhub-ETL-main/
        ├── airflow/                   # Airflow DAGs for batch orchestration
        ├── fraudguard/                # Real-time streaming fraud prevention & score engine
        ├── docker/                    # Spark batch & streaming container setups
        └── src/                       # Medallion lakehouse pipeline (Bronze → Silver → Gold)
```

---

## 🚀 Key Modules & Capabilities

### 1. E-Commerce Platform & FraudGuard Engine (`Webiste/`)
* **Full-Stack Application:** Responsive React 18 frontend paired with an Express/TypeScript backend and MySQL relational database.
* **Event-Driven Telemetry:** Captures user clickstream and transactional events asynchronously via **Apache Kafka (KRaft)**.
* **FraudGuard Risk Detection:** Real-time evaluation of behavioral attack vectors (brute-force logins, credential stuffing, card testing, account takeovers, coupon abuse, and scraper bots) with automated enforcement (OTP step-up, restrictions, admin alerts).

### 2. Medallion Lakehouse ETL Platform (`ETL/`)
* **Spark Structured Streaming:** Continuous ingestion of live Kafka events into immutable raw **S3 Bronze** storage.
* **Silver Cleansing & Deduplication:** Cleanses, standardizes, and deduplicates records with Kafka offset tracking in **S3 Silver**.
* **Gold Dimensional Modeling:** Transforms operational telemetry into an analytical **Kimball Star Schema** cataloged by **AWS Glue** and queried with **Amazon Athena**.
* **Airflow Orchestration:** Automated scheduling and dependency management for batch pipelines.

---

## 🛠️ Tech Stack

* **Frontend:** React, TypeScript, Vite, Tailwind CSS
* **Backend:** Node.js, Express, TypeScript, MySQL
* **Streaming & Messaging:** Apache Kafka (KRaft)
* **Big Data Processing:** Apache Spark (PySpark), Spark Structured Streaming
* **Workflow Orchestration:** Apache Airflow
* **Cloud & Storage:** AWS S3, AWS Glue, Amazon Athena, RDS
* **Containerization:** Docker & Docker Compose
