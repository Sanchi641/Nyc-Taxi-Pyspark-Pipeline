NYC Taxi Data Analytics & Engineering Platform
A robust batch data pipeline project using PySpark and Databricks, built as part of a Data Engineering Technical Assessment. This project processes NYC TLC Yellow & Green taxi trip data to power analytics through a dimensional model, performance-optimized Spark jobs, and insightful SQL queries.

🧭 Project Summary
 Built a modular ETL pipeline with PySpark on Databricks

 Processed 3 months of NYC Yellow & Green taxi trip data

 Designed a Star Schema for analytical workloads

 Applied data quality rules, outlier filtering, and aggregations

 Created reusable analysis queries to uncover revenue patterns and ride behaviors

🏗️ Architecture & Data Flow
Ingest raw CSV files → transform with PySpark → write Delta tables

Star Schema model supports fast querying and reporting

Stored curated data in Azure Data Lake

Partitioned by time/location for optimization

Prepared for future enhancements like streaming ingestion

 Architecture Diagram

🧠 Data Modeling Highlights
Component	Description
✅ fact_trips	Trip-level fact table with cleaned and enriched data
✅ Dimensions	Zones, Rate Codes, Payment Types
📦 SCD Types	Type 2 for Zones & Payment Types, Type 1 for Rate Codes
📊 Aggregations	Revenue trends, long trips, weekday/weekend patterns

📄 View Model Design

🔁 ETL Logic (PySpark)
Implemented in combined_taxi.ipynb:

🧮 Trip duration & average speed computation

🚫 Outlier detection (e.g., 0 fare, abnormal durations)

🔗 Zone enrichment via joins

📆 Time-based partitioning (hour/day/month)

📊 Aggregation tables for revenue and trip analysis

✅ Data validation and quality enforcement

📊 Analysis & Business Queries
💰 Top 10 Pickup Zones by Revenue
queries/top_10_pickups.sql

📅 Trip Patterns: Weekday vs Weekend
queries/weekday_weekend_patterns.sql

🛣️ Top 10 Longest Trips (>10 miles)
queries/top_10_long_trips.sql

🚀 Performance & Optimization
⚡ Broadcast joins for small lookup tables

🧊 Delta Lake + predicate pushdown

🧱 Partitioning by pickup datetime and zone

🧮 Pre-aggregated summary tables for BI tools

🔍 Indexed keys and compacted tables for efficiency

🗂️ Folder Structure
bash
Copy
Edit
nyc-taxi-data-platform/
├── notebooks/              # PySpark ETL scripts
├── docs/                   # Architecture and model docs
├── queries/                # SQL analysis queries
├── README.md
├── requirements.txt
🛠️ Tech Stack
🐍 PySpark & Spark SQL

🔥 Databricks (Spark runtime on Azure)

🌊 Azure Data Lake + Delta Lake

🧱 Star Schema, SCD Type 1 & 2

🗃️ SQL for analytical querying

▶️ How to Run
Upload the notebook to your Databricks workspace

Attach to a Spark 3.x-compatible cluster

Add NYC TLC Yellow & Green taxi CSVs (3 months)

Run all cells to generate fact/dimension/aggregate tables

Use SQL queries or views for analytics

📎 Key Resources
📝 docs/dimensional_model.md: Data warehouse schema

📊 notebooks/combined_taxi.ipynb: Full ETL & pipeline logic

📈 queries/: SQL queries for 2024 analytics

📄 License
MIT License – use freely for learning, interview prep, or extending your own data engineering workflows.

