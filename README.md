# MovieLens

An end-to-end ELT pipeline that transforms MovieLens datasets into analytics-ready models using dbt and Snowflake, with data ingestion from Amazon S3.

---

## Features

- **Batch ELT Pipeline:** Load MovieLens CSV datasets from Amazon S3 into Snowflake for warehouse processing.
- **Staging Models:** Clean and standardize raw movie, rating, tag, and genome-score data.
- **Dimensional Modeling:** Organize transformations into dimension tables, fact tables, and a reporting mart.
- **Incremental Processing:** Process new rating records incrementally to reduce unnecessary reprocessing.
- **Data Quality Testing:** Apply dbt tests, including nullability and relationship checks, to validate data integrity.
- **Historical Tracking:** Use timestamp-based snapshots to track changes in tag data over time.
- **Analytics-Ready Data:** Structure transformed datasets for downstream reporting and analysis.

---

## Tech Stack

- **Transformation:** dbt
- **Data Warehouse:** Snowflake
- **Data Storage:** Amazon S3
- **Query Language:** SQL
- **Data Modeling:** Staging, dimensional modeling, fact tables, and reporting marts

---

## Architecture

1. **Data Ingestion:** Store MovieLens CSV files in Amazon S3.
2. **Data Loading:** Configure Snowflake stages and use `COPY INTO` to load files into raw tables.
3. **Staging Layer:** Clean and standardize source data using dbt staging models.
4. **Transformation Layer:** Build dimension and fact models from staged datasets.
5. **Incremental Processing:** Update the ratings model incrementally as new records arrive.
6. **Historical Tracking:** Capture tag data changes using timestamp-based dbt snapshots.
7. **Reporting Mart:** Publish analytics-ready models for downstream querying and reporting.

---

## Data Models

The pipeline works with four primary MovieLens datasets:

- **Movies:** Movie metadata and identifiers.
- **Ratings:** User ratings associated with movies.
- **Tags:** User-generated movie tags.
- **Genome Scores:** Movie relevance scores associated with genome tags.

These datasets are transformed into staging models, dimensional models, fact tables, and a reporting mart.

---

## Data Quality and History

- **Null Tests:** Identify unexpected missing values in modeled data.
- **Relationship Tests:** Validate relationships between related models.
- **Incremental Models:** Process rating data without rebuilding the entire dataset on every run.
- **Snapshots:** Track historical changes in tag data using timestamps.

---

## Key Engineering Concepts

- Batch ELT architecture
- Cloud data warehousing
- SQL-based transformations
- Dimensional data modeling
- Incremental data processing
- Data quality validation
- Historical data tracking
- Analytics-ready data marts

---

## Author
**Sanvi Mahajan** (✿◡‿◡)
