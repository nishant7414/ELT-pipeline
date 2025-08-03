# 🚀 End-to-End ELT Data Pipeline

This repository contains a robust, production-ready **ELT (Extract, Load, Transform)** pipeline built using **Python**, **Docker**, and **dbt**. The pipeline automates the extraction of data from a source database, loads it into a destination warehouse, and transforms it using dbt for analytical purposes.

---

## 📌 Features

- 🔄 **Extract**: Connects to the source database and pulls data efficiently.
- 📥 **Load**: Loads raw data into the destination database.
- 🛠️ **Transform**: Leverages **dbt** to apply business logic and prepare clean, analytics-ready data.
- 🐳 **Dockerized**: Run the entire pipeline in isolated containers for consistent execution.
- 🕒 **Scheduled Automation**: Easily schedule runs using **cron jobs**.

---

## 🧩 Architecture Workflow

```text
   [Source Database] 
         ⬇
      Extraction
         ⬇
  [Raw Layer in Destination DB]
         ⬇
     Transformation (dbt)
         ⬇
  [Cleaned & Modeled Data]
```


## 🛠️ Technologies Used

| Component     | Tool / Framework         |
| ------------- | ------------------------ |
| Language      | Python                   |
| Orchestration | Subprocess + Cron Jobs   |
| Data Modeling | dbt                      |
| Containers    | Docker + Docker Compose  |
| Database      | PostgreSQL (replaceable) |


## 🚀 Getting Started

✅ Prerequisites

``` bash
   Install Docker

   Install Python and pip

   Install dbt:
```
```bash 
  pip install dbt-core dbt-postgres --user
```

## 📦 Setup & Run

``` bash
## 1. Clone the Repository:

git clone https://github.com/Shubham11440/ELT-pipeline.git
cd ELT-pipeline

## 2. Configure Database Connections:

Update credentials inside the config/ directory.

Example config files:

      config/source_db_config.yaml

      config/destination_db_config.yaml

## 3. Set Up dbt:

      Go to the elt/dbt_project/ directory.

Update profiles.yml for your DB connection.

## 4. Build Docker Containers:

     docker-compose up --build

## 5. Run the Pipeline:

Manually:

   python run_pipeline.py

Or schedule it using a cron job:

      0 2 * * * /usr/bin/python3 /path/to/ELT-pipeline/run_pipeline.py

## 6. Stop & Clean Up:

      docker-compose down -v

```

## 📁 Project Structure

```
ELT-pipeline/
│
├── config/               # YAML configs for DB connections
├── elt/                  # Core pipeline scripts
├── custom_postgres/      # Optional PostgreSQL setup
├── logs/                 # Logging directory
├── source_db_init/       # SQL seed scripts for source DB
├── docker-compose.yaml   # Docker setup
├── start.sh              # Startup script
└── README.md             # Project documentation
```

## 📘 Documentation

🔧 Configuration Guide → docs/configuration.md

📊 dbt Setup & Usage → docs/dbt.md

🐳 Docker Instructions → docs/docker.md

