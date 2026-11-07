# Team 5 | Checkpoint 3 Agile Approach

**Team members:** Boomikaa P, Chahatleen Kaur, Saba Gul, Vanshika Malviya, K. Shreya, and Tushar Rathor.

## Project goal

Build a reliable data pipeline for the UCI Online Retail II dataset. The later dashboard will help a UK online gift shop decide which customers, products, and countries to focus on. This project gives the team practice with data engineering and data modeling skills.

## What we are building at checkpoint 3

The checkpoint 3 notebook creates a cleaned working copy first, then performs **exploratory data analysis (EDA)** on that copy to measure size, missing values, duplicates, dates, numeric ranges, and country counts. It preserves the original rows in a **Bronze** table, then saves cleaned data and quality results in **Silver** tables. The requested Databricks names are catalog `retail_catalog`, schema `team5_retail`, and volume `retail_files`. Bronze keeps the incoming records and load details. Silver standardizes values, removes exact duplicate rows, flags missing customer IDs, separates cancelled invoices, and records basic quality measures. **Gold** tables and the dashboard are the next checkpoint's work.

## Agile approach

We use a small-step Agile workflow. The team keeps a shared **backlog** (the list of tasks), meets for a 15-minute weekly **stand-up** (what is done, what is blocked, and what comes next), and records problems and learning in a shared log. Each task has an owner and a simple completion check. At each **review**, a teammate looks at the work and the team adjusts the next tasks.

We test on a small sample before running the full dataset, because the file is large and Databricks Free Edition has a daily compute quota. Each member should run the finished notebook in their own account and be ready to explain the steps. If AI helps with code or writing, record that in the learning log.

## Increments and ownership

| Increment | What shows it is complete | Suggested owners, based on the checkpoint 2 plan |
|---|---|---|
| Load (Bronze) | Both CSVs are in Delta Bronze; row count and load timestamp are recorded | Chahatleen, K. Shreya, Tushar |
| Clean (Silver) | Types and text are standardized; exact duplicates removed; cancellations split out; missing IDs flagged | Chahatleen, Saba, K. Shreya |
| Quality review | Input/output counts and key issue rates are saved in a quality log | Saba, Boomikaa, K. Shreya |
| Model for checkpoint 4 | Logical model and Gold table plan are reviewed | Boomikaa, Vanshika, Saba |
| Business story for checkpoint 4 | Dashboard questions and explanation are agreed | Vanshika, Chahatleen |


## GitHub links

- Repository: [Big Data Analysis Project](https://github.com/Vanshika050503/Big-Data-Analysis-Project.git)
- Project board: [Team project board](https://github.com/users/Vanshika050503/projects/6)

## Simple glossary of big data terms

1. Big data: data large enough that a distributed system can process it across multiple machines.
2. Batch processing: processing a saved group of records together; this project is batch work, not live streaming.
3. ETL / ELT: Extract, Transform, Load; or Extract, Load, Transform. We load the source into Bronze, then transform it into Silver.
4. Lakehouse: one platform that stores data like a data lake and supports managed tables and analytics like a data warehouse.
5. Delta table: a table format used by Databricks that tracks changes and supports reliable table operations.
6. Bronze / Silver / Gold: raw, cleaned, and analysis-ready stages of a lakehouse. Checkpoint 3 builds Bronze and Silver; checkpoint 4 plans Gold.
7. Schema: the field names and data types that describe a table.
8. Data quality: checks that show whether records are complete, valid, and consistent.
9. Data lineage / provenance: information about where data came from and when it was loaded.
10. Unity Catalog Volume: a governed file location in Databricks where the team can store input CSV files.

## Governance and success

The dataset is Online Retail II from the UCI Machine Learning Repository, licensed CC BY 4.0. Credit: Chen, D. (2012), *Online Retail II* [Dataset], https://doi.org/10.24432/C5CG6D. Customer IDs are used only as anonymous keys; the team will not try to identify people. Missing IDs and unusual prices or quantities are reported, not silently hidden.

