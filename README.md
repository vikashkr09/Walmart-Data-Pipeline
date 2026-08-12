# 🚀 Walmart End-to-End Data Engineering Pipeline

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?logo=databricks)
![Delta Lake](https://img.shields.io/badge/Delta-Lake-blue)
![dbt](https://img.shields.io/badge/dbt-Transformations-orange)
![Apache Airflow](https://img.shields.io/badge/Apache-Airflow-red?logo=apacheairflow)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker)
![AWS S3](https://img.shields.io/badge/AWS-S3-FF9900?logo=amazonaws)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?logo=postgresql)

An **End-to-End Data Engineering Pipeline** demonstrating modern ELT architecture using **AWS S3, Ghost (PostgreSQL), Databricks, Delta Lake, dbt, Apache Airflow, Docker, and PostgreSQL**.

The project ingests operational data, performs incremental loading with Change Data Capture (CDC), builds analytical models using dbt, validates data quality, and orchestrates the complete workflow using Apache Airflow.

---

# 🏗️ Project Architecture

<img width="1825" height="877" alt="Architecture" src="https://github.com/user-attachments/assets/b77629bd-8ca4-4d78-8b82-31e464623a38" />

---

# 📌 Overview

This project demonstrates how modern data engineering pipelines are built in production.

The pipeline ingests operational data from multiple source tables, performs incremental loading into Databricks Delta Lake, creates a unified analytical layer, applies business transformations using dbt, validates data quality, and produces business-ready fact models.

The project follows an ELT approach where heavy transformations are performed inside the data platform rather than before loading.

---

# 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Programming | Python |
| Storage | AWS S3 |
| Source Database | Ghost (PostgreSQL) |
| Processing Engine | Databricks (Apache Spark Runtime) |
| Storage Format | Delta Lake |
| Transformation | dbt |
| Workflow Orchestration | Apache Airflow |
| Metadata Database | PostgreSQL |
| Message Broker | Redis |
| Containerization | Docker |
| Version Control | Git & GitHub |
| IDE | VS Code |

---

# 📂 Source Dataset

The pipeline processes six operational tables:

- Customers
- Employees
- Orders
- Order Items
- Products
- Stores

Each table contains represents a transactional retail dataset.

---

# ⚙️ End-to-End Pipeline

```text
                 CSV Files
                      │
                      ▼
          Ghost (PostgreSQL Database)
                      │
                 CDC Detection
                      │
                      ▼
                AWS S3 Data Lake
                      │
                      ▼
     Databricks (Apache Spark Runtime)
                      │
      Incremental MERGE + Delta Tables
                      │
                      ▼
                Silver Layer
            (One Big Table - OBT)
                      │
          Data Quality Validation
                      │
                      ▼
           dbt Transformations
                      │
         Dimension & Fact Models
                      │
                      ▼
         Business Ready Gold Layer
```

---

# 🏛️ Data Architecture

The project follows a modern ELT architecture.

```
Sources
    │
    ▼
Silver Layer
    │
    ▼
One Big Table (OBT)
    │
    ▼
Dimension Models
    │
    ▼
Fact Models
```

---

# 🔄 Incremental Data Loading

Databricks performs incremental ingestion from the operational database.

Implemented features include:

- Delta Table Creation
- Incremental Loading
- CDC (Change Data Capture)
- MERGE Operations
- Upserts

This minimizes processing time and avoids full table reloads.

---

# 📊 dbt Transformation Layer

dbt is responsible for transforming the curated Silver data into analytical models.

Implemented features include:

- Sources
- Incremental Models
- One Big Table (OBT)
- Gold Layer Models
- Dimension Tables
- Fact Tables
- Macros
- Documentation
- Data Quality Testing

---

# ✅ Data Quality

The project validates data quality using built-in dbt tests.

Current tests include:

- Unique
- Not Null

Additional tests can easily be added as the project grows.

---

# 🌪️ Workflow Orchestration

Apache Airflow orchestrates the complete pipeline.

Workflow:

```
Trigger Pipeline
        │
        ▼
Run dbt Models
        │
        ▼
Run dbt Tests
        │
        ▼
Pipeline Success
```

Airflow ensures reliable scheduling, monitoring, and execution of the complete workflow.

---

# 📁 Project Structure

```text
WALMART_DE_PROJECT
│
├── Airflow_Dbt_Project/
│   ├── dags/
│   ├── plugins/
│   ├── config/
│   ├── walmart_project/
│   │   ├── models/
│   │   ├── macros/
│   │   ├── snapshots/
│   │   ├── seeds/
│   │   ├── tests/
│   │   ├── analyses/
│   │   ├── dbt_project.yml
│   │   └── profiles.yml
│   │
│   ├── docker-compose.yaml
│   ├── Dockerfile
│   ├── requirements.txt
│   └── .env
│
├── DE_PROJECT/
│   ├── src/
│   ├── walmart_dataset/
│   ├── pyproject.toml
│   └── uv.lock
│
├── images/
│   └── architecture.png
│
└── README.md
```

---

# 🚀 Running the Project

Clone the repository

```bash
git clone https://github.com/vikashkr09/Walmart-Data-Pipeline.git
```

Navigate into the project

```bash
cd WALMART_DE_PROJECT
```

Install dependencies

```bash
pip install -r Airflow_Dbt_Project/requirements.txt
```

Start Airflow

```bash
docker compose up -d
```

Verify containers

```bash
docker compose ps
```

Run dbt

```bash
dbt debug

dbt deps

dbt run

dbt test
```

---

# 💡 Features

- End-to-End ELT Pipeline
- Incremental Data Loading
- CDC Processing
- Delta Lake
- One Big Table (OBT)
- Dimension & Fact Modeling
- dbt Documentation
- dbt Data Testing
- Airflow Orchestration
- Dockerized Environment
- AWS S3 Integration
- Databricks Integration
- Production-style Architecture

---

# 📚 Skills Demonstrated

- Data Engineering
- Data Modeling
- ETL / ELT Pipelines
- Apache Airflow
- Databricks
- Delta Lake
- dbt
- SQL
- Python
- Docker
- PostgreSQL
- Incremental Processing
- Change Data Capture (CDC)
- Data Quality
- Git & GitHub

---

# 🔮 Future Improvements

- CI/CD using GitHub Actions
- Automatic Data Validation
- Great Expectations Integration
- Data Lineage Visualization
- Monitoring & Alerting
- Slack Notifications
- Unit Testing
- Terraform Deployment

---

# 👨‍💻 Author

**Vikash Kumar**

Data Engineer | Python | SQL | dbt | Databricks | Airflow | Docker | Delta Lake

GitHub: https://github.com/vikashkr09

---

⭐ If you found this project useful, consider giving it a star!
