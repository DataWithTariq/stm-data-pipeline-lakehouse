# STM Montreal - Real-Time Data Lakehouse

## Project Description
Implementation of an end-to-end data pipeline to ingest and process STM (Société de transport de Montréal) bus positions. This project follows the Medallion Architecture to transform raw GTFS-Realtime data into analytical assets.

## Architecture & Design
The system is built on a Lakehouse architecture using Databricks and Delta Lake.

1. **Bronze Layer**: Raw ingestion of Protobuf (API) to Delta tables. 
   - Frequency: Every 5 minutes.
   - Storage: Unity Catalog Volumes (.pb files) + Delta Table (Metadata & Raw Parse).
2. **Silver Layer**: Data cleaning and enrichment (Current focus).
   - Deduplication of static bus positions.
   - Coordinate validation and timestamp normalization.
3. **Gold Layer**: Analytical aggregates for visualization (Planned).

## Technical Stack
- **Compute**: Apache Spark / Databricks
- **Storage**: Delta Lake (ACID Transactions)
- **Orchestrator**: Databricks Workflows
- **Format**: GTFS-Realtime (Protobuf)
- **Language**: PySpark, SQL

## Repository Structure
- `/notebooks`: Core logic for Ingestion and Transformation.
- `/sql`: DDL scripts for table initialization.
- `/config`: JSON configurations for environment parameters.
