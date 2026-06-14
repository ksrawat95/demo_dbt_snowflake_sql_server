# Demo dbt Snowflake SQL Server

## Project Overview
This repository contains a demonstration dbt (Data Build Tool) project showcasing data transformation workflows. It integrates with Snowflake and SQL Server databases to load seed datasets, configure staging schemas, implement slowly changing dimension (SCD) tests, and compile views and table models.

## Tech Stack
- **dbt (Data Build Tool)**: Core tool for data transformation modeling, testing, and documentation.
- **SQL / PLpgSQL / TSQL**: Languages used for database queries and logical modeling.
- **Snowflake / Microsoft SQL Server**: Database back-ends for data storage and compute execution.
- **YAML**: Configuration files for project definitions and testing assertions.

## Key Implementation Details
- **dbt Project Configuration (`dbt_project.yml`)**: Sets the execution profile, paths for models, analysis, tests, seeds, and macros, and specifies staging materialization schemas (e.g., table/view schemas under `staging`).
- **Data Models (`models/`)**:
  - `src.yml`: Source configurations detailing tables like `Source_SCD` under schema `dbo` and database `SCD_LEARN`, along with unique/not-null assertions.
  - `scv_model_view/view_csv.sql`: Materializes CSV dataset configurations via dbt references (`{{ ref('test_csv') }}`).
  - `stg_tables/`: Contains staging models (`stg_test.sql`, `ref_stg_tables.sql`) materialized as tables or views in target schemas.
- **Macros, Seeds, & Snapshots**: Includes structure for custom dbt macros, seed files under `data/`, and database snapshot configurations for auditing historical data changes.
