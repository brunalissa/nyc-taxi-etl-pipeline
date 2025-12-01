##⭐ NYC Taxi ETL Pipeline
A production-inspired, end-to-end data engineering pipeline designed to demonstrate technical depth, architectural clarity, and real-world engineering standards.
📌 Executive Summary

This project delivers a complete batch ETL pipeline for NYC Yellow Taxi trip data, built using Python, Pandas, Parquet, and SQLite, following professional data engineering conventions.
It was designed with the mindset of real production systems: clear modularization, reproducibility, data quality validation, schema enforcement, structured outputs, and scalability in mind.

The pipeline transforms messy, raw CSV trip data into clean, analytics-ready datasets stored in Parquet and SQL — mirroring what a Data Engineer would build in a real company.

🟨 This is not an academic exercise.
🟨 It simulates how a junior–mid data engineer operates in a real data environment.

🎯 Core Objectives

This project was created to showcase:

Realistic data ingestion → transformation → quality checks → output architecture

Clean modular Python code

A standard ETL folder structure that mimics production pipelines

Schema enforcement and data integrity principles

Professional documentation and engineering communication

Ability to reason about data, not only process it

🧱 Architectural Overview
nyc-taxi-etl-pipeline/
├── data/
│   ├── raw/               # Raw CSVs (source-of-truth)
│   └── processed/         # Cleaned, validated Parquet files
├── src/
│   └── etl/
│       ├── transform.py   # Business rules + data standardization
│       ├── load.py        # Database layer (SQLite)
│       └── run.py         # Pipeline orchestration
├── notebooks/             # Exploratory EDA
├── tests/                 # Data quality validations
└── README.md


Each folder has a specific, isolated responsibility.
This separation ensures maintainability, testability, and clarity of ownership.

⚙️ Technologies & Rationale
Tech	Why It Was Chosen
Python	Most widely used language in data engineering for ETL and orchestration.
Pandas	Ideal for batch processing and rich data manipulation.
Parquet	Modern, columnar, compressed — used in lakehouses and modern analytics pipelines.
PyArrow	Industry-standard backend for Parquet.
SQLite	Lightweight SQL engine to simulate a real warehouse load.
VS Code + Git	Clean workflow, reproducibility, version control.
🔄 Pipeline Flow (High-Level)
1. Raw Data Intake

Reads Taxi CSV files

Standardizes column names

Validates required fields

2. Transformation & Cleaning Layer

Includes professional-grade rules like:

Duplicate removal

Timestamp parsing with coercion

Numeric type casting with fallback behavior

Negative distance filtering

Canonical column schema enforcement

The goal: trustworthy, consistent data.

3. Data Validation

Data quality checks ensured by tests:

Schema consistency

Non-null critical features

No negative distances

Valid timestamps

Duplicate prevention

This mimics real DQ workflows in companies.

4. Output Layer

Processed output is written as:

✔️ Parquet file

(optimized for analytics, lakehouses, and scalable querying)

✔️ SQLite table

(simulating a warehouse ingestion layer)

📊 Deliverables

This project produces:

📁 A cleaned Parquet dataset

Optimized for downstream analytics, ML, BI, or Lakehouse ingestion.

🗄️ A SQLite database

Containing structured, ready-to-query taxi trip tables.

📘 A Jupyter EDA notebook

Documenting initial data exploration and decisions.

🧪 Data quality test suite

Reflecting real engineering expectations.

💡 Engineering Decisions & Rationale
Why Parquet?

Because modern data platforms (Databricks, Snowflake, BigQuery, AWS Lake Formation) rely heavily on columnar formats.
Delivering Parquet shows familiarity with enterprise-grade analytics storage.

Why a modular architecture?

Because real ETL pipelines are rarely a single script.
They are composed of layers with isolated responsibilities.

Why schema enforcement?

Because inconsistent schema is the number 1 cause of broken production pipelines.

Why SQLite?

To simulate a data warehouse load stage without external dependencies.

📂 How to Run Locally
1. Create virtual environment
python -m venv .venv

2. Activate environment

Windows:

.venv\Scripts\activate


Mac/Linux:

source .venv/bin/activate

3. Install packages
pip install -r requirements.txt

4. Run the pipeline
python src/etl/run.py

🧭 Future Enhancements (Roadmap)

To evolve this into a production-grade case:

 Docker containerization

 Airflow orchestration (DAG version)

 dbt transformation layer

 Logging with Python's logging module

 Automatic unit tests in GitHub Actions

 Metadata layer (data dictionary + expectations)

 Partitioned Parquet output

🏆 Key Competencies Demonstrated

This project highlights capabilities essential to data engineering roles:

Data modeling mindset

Ability to clean and validate messy real-world data

Production-like architecture design

Understanding of modern file formats

SQL loading logic

Reproducible environment setup

High-quality documentation and communication

This is the type of project managers love to see: structured, clear, and reliable.

📬 Contact

If you’d like to discuss the architecture, design choices, or see an extended pipeline version (Airflow / Docker), feel free to reach out.
