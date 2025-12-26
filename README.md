# STM Real-Time Bus Tracking Pipeline (Lakehouse)

## 📌 Project Overview
End-to-end data engineering project to ingest, transform, and visualize Montreal (STM) bus positions in real-time. 
The goal is to build a scalable **Medallion Architecture** using Databricks and Delta Lake.

## 🏗️ Architecture
- **Source**: STM GTFS-Realtime API (Protobuf)
- **Ingestion (Bronze)**: Python/Spark job running every 5 minutes. Raw files stored as `.pb` in UC Volumes.
- **Transformation (Silver)**: (In Progress) Cleaning, deduplication, and schema enforcement.
- **Serving (Gold)**: (Planned) Business-ready aggregates for Power BI.

## 🛠️ Tech Stack
- **Platform**: Databricks (Community Edition)
- **Storage**: Delta Lake / Unity Catalog (Volumes)
- **Language**: Python (PySpark), SQL
- **Orchestration**: Databricks Workflows (Job Scheduler)
