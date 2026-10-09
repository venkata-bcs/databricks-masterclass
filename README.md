# Databricks

> (c) Venkata Bhattaram

# Learning Paths

| Path | Modules | Target certification |
|------|---------|----------------------|
| Beginner (Quick Start) | 1, 2, 5, 6, 7, 22, 23 | — |
| Data Engineer | 1 – 15, 18, 19, 20, 22 | Data Engineer Associate / Professional |
| Data Analyst | 1 – 3, 6, 7, 16, 22 | Data Analyst Associate |
| ML / GenAI Engineer | 1 – 7, 17 – 20 | ML Associate / Professional, GenAI Engineer Associate |

# Topics

## Part I — Getting Started

## 1. Introduction to Databricks & the Lakehouse
- Why Databricks? Problems with siloed data lakes and data warehouses
- What Databricks is: a unified Data Intelligence Platform built on Apache Spark
- The Lakehouse architecture: data lake flexibility + data warehouse reliability, one platform for BI, data engineering and AI
- Control plane vs. compute plane (classic and serverless)
- Databricks on AWS, Azure and GCP
- Account console vs. workspace; editions and pricing (DBUs)
- Real-world use cases across industries

## 2. Setting Up Databricks
- Signing up (Free Edition / free trial) and choosing a cloud
- Exploring the workspace interface: sidebar, Catalog Explorer, Workspace browser, compute, jobs, SQL
- Creating and running your first notebook
- Attaching compute and running cells
- Importing sample data and the `samples` catalog

## 3. Workspace & Development Environment
- Workspace UI: folders, Git folders (Repos)
- Notebooks: languages (Python, SQL, Scala, R), magic commands (`%sql`, `%run`, `%pip`, `%fs`)
- `dbutils`: file system, secrets, widgets, notebook workflows
- Databricks CLI, REST API and SDKs
- Databricks Connect and IDE integration (VS Code, PyCharm)
- Databricks Asset Bundles (DABs) for project packaging

## 4. Compute
- All-purpose clusters vs. job clusters
- Serverless compute for notebooks, jobs and SQL
- Databricks Runtime versions (Standard, ML, Photon)
- Cluster sizing, autoscaling, auto-termination
- Cluster policies, pools and access modes (standard/shared, dedicated/single user)
- Libraries: cluster-scoped, notebook-scoped and init scripts

## Part II — Core Skills

## 5. PySpark Basics & Apache Spark on Databricks
- Spark architecture: driver, executors, jobs, stages, tasks
- Creating DataFrames (from lists, dictionaries, files, tables)
- Inspecting DataFrames: `show`, `display`, `printSchema`, `describe`, `count`
- Transformations: `select`, `filter`, `withColumn`, `groupBy`, `orderBy`, `drop`
- Reading CSV files: headers, schema inference vs. explicit schemas
- Reading and writing other formats (JSON, Parquet, Delta, JDBC)
- Transformations vs. actions, lazy evaluation
- Joins, aggregations, window functions, UDFs and Pandas UDFs
- RDDs, Spark SQL and Pandas API on Spark
- Spark UI and query plans (`explain`)

## 6. Delta Lake Fundamentals
- What Delta Lake is and why it matters: transaction log (`_delta_log`), ACID guarantees
- Reading and writing Delta tables (DataFrame API and SQL)
- Managed vs. external tables
- CRUD operations: `INSERT`, `UPDATE`, `DELETE`, `MERGE INTO` (upserts)
- Time travel (`VERSION AS OF`, `TIMESTAMP AS OF`), `DESCRIBE HISTORY`, `RESTORE`
- Schema enforcement and schema evolution
- `OPTIMIZE`, `VACUUM`, Z-Ordering and Liquid Clustering
- Change Data Feed (CDF)
- Deletion vectors, constraints, generated and identity columns
- Delta UniForm (Iceberg / Hudi interoperability)

## 7. SQL in Databricks
- Creating, querying and managing Delta tables with SQL
- Databases (schemas), tables, views, temporary views
- `CREATE TABLE AS SELECT` (CTAS)
- Common table expressions (CTEs), joins, subqueries, window functions
- Higher-order functions and working with arrays, structs and JSON
- `DESCRIBE`, `SHOW`, table properties and comments

## Part III — Data Engineering

## 8. Data Ingestion & Lakeflow Connect
- Batch vs. streaming ingestion
- CTAS and `COPY INTO` for idempotent batch loads
- Auto Loader (`cloudFiles`) for incremental file ingestion, schema inference and evolution
- Handling JSON and semi-structured data
- Rescued data column (`_rescued_data`) for malformed or unexpected fields
- Lakeflow Connect: standard and managed connectors (SaaS apps, databases)
- Upload UI and Unity Catalog volumes for files
- Ingesting from Kafka, Event Hubs, Kinesis

## 9. Data Transformation & Medallion Architecture
- Bronze, Silver, Gold layers and their responsibilities
- Data manipulation with SQL and PySpark
- Batch vs. incremental processing
- Slowly Changing Dimensions (SCD Type 1 & 2)
- Data quality checks, cleansing and deduplication
- Dimensional modeling for analytics (facts and dimensions)
- Best practices for pipeline design

## 10. Structured Streaming
- Streaming concepts: micro-batches, triggers, checkpoints
- Output modes: append, update, complete
- Watermarking and late data handling
- Stateful operations, stream-stream and stream-static joins
- `foreachBatch` and streaming into Delta tables

## 11. Lakeflow Spark Declarative Pipelines (formerly Delta Live Tables)
- Streaming tables and materialized views
- Declarative pipeline definitions in SQL and Python
- Expectations for data quality (warn, drop, fail)
- Change data capture (CDC) with `AUTO CDC` / `APPLY CHANGES`, SCD Type 1 & 2
- Pipeline modes: triggered vs. continuous, development vs. production
- Event logs, lineage and monitoring

## 12. Orchestration with Lakeflow Jobs
- Building multi-task jobs as Directed Acyclic Graphs (DAGs)
- Task types: notebook, Python script, wheel, SQL, pipeline, dbt, JAR
- Task dependencies, conditional (`if/else`) and `for each` tasks
- Parameters, task values and job parameters
- Job scheduling: cron schedules, file-arrival and table-update triggers
- Retries, timeouts, alerts and notifications
- Repair runs, run history and monitoring

## 13. Governance & Security with Unity Catalog
- Metastore, catalogs, schemas, tables, views, volumes
- Three-level namespace (`catalog.schema.table`)
- Privileges and access control (`GRANT` / `REVOKE`), ownership
- Storage credentials and external locations
- Row filters and column masks
- PII handling and data privacy (masking, tagging, data deletion / right-to-be-forgotten)
- Data lineage, audit logs and system tables
- Tags, data discovery and Catalog Explorer
- Lakehouse Federation (querying external databases)
- Delta Sharing and Databricks Marketplace

## 14. Platform Security
- Identity: users, groups, service principals, SCIM
- Authentication: SSO, personal access tokens, OAuth
- Secrets management (secret scopes)
- Network security: private link, IP access lists, VPC/VNet injection
- Encryption at rest and in transit, customer-managed keys
- Compliance security profile

## 15. Performance Optimization
- Spark UI analysis: jobs, stages, tasks, SQL/DataFrame tab
- Partitioning vs. Liquid Clustering
- Data skipping, file sizing, small-file problem
- Caching (disk cache, Spark cache)
- Adaptive Query Execution (AQE), broadcast joins
- Shuffle tuning, skew handling, spill
- Cluster sizing and choosing the right compute
- Predictive Optimization

## Part IV — Data Analysis

## 16. Databricks SQL, Dashboards & AI/BI
- SQL warehouses: serverless, pro, classic
- SQL editor: writing, saving and scheduling queries; query history
- Building analytical tables and managing database objects
- Visualizations: creating charts and tables from query results
- Parameter-driven queries and dashboard filters
- AI/BI Dashboards for interactive reporting
- AI/BI Genie spaces for conversational, natural-language data querying and automated insights
- Alerts: configuring thresholds and notifications
- Connecting BI tools (Power BI, Tableau) via JDBC/ODBC
- Photon engine and query performance

## Part V — Machine Learning, Generative AI & MLOps

## 17. Machine Learning & MLOps
- Databricks Runtime for ML
- Model training with Spark ML, scikit-learn and other frameworks
- MLflow: experiment tracking, model logging, model registry in Unity Catalog
- Feature engineering and Feature Store
- AutoML and hyperparameter tuning
- Model Serving (real-time endpoints) and batch inference
- Deploying scalable ML pipelines; model lifecycle (champion/challenger, aliases)
- Lakehouse Monitoring for data and model quality

## 18. Generative AI & AI Agents (Mosaic AI)
- Foundation Model APIs and external models
- AI Functions in SQL (`ai_query`, `ai_summarize`, etc.)
- Vector Search and Retrieval-Augmented Generation (RAG)
- Agentic application design with the Mosaic AI Agent Framework
- Agent evaluation with MLflow (evaluation datasets, LLM judges, tracing)
- AI Gateway: governance, rate limits, guardrails
- Fine-tuning models

## 19. Apps & Operational Data
- Databricks Apps (Streamlit, Dash, Gradio, Flask)
- Lakebase (managed Postgres) for operational workloads
- Online tables for low-latency serving

## Part VI — Production & Operations

## 20. DevOps & CI/CD
- PySpark code modularization (packages, reusable functions, wheels)
- Unit testing with `pytest`; integration testing of notebooks and pipelines
- Git integration and branching strategies
- Databricks Asset Bundles for automated deployment across environments
- CI/CD with GitHub Actions / Azure DevOps
- Infrastructure as Code with Terraform

## 21. Monitoring, Cost Management & Administration
- System tables for billing, usage and audit
- Budgets, tags and cost attribution
- Workspace administration and account-level settings
- Cluster and job monitoring, logs and metrics

## Part VII — Projects & Wrap Up

## 22. Mini End-to-End Lakehouse Project: Sales Data Pipeline
- Ingest raw sales data (CSV/JSON) into Bronze with Auto Loader
- Clean, deduplicate and conform data into Silver
- Build aggregated Gold tables (revenue by region, product, period)
- Orchestrate the pipeline with Lakeflow Jobs
- Govern tables with Unity Catalog
- Visualize results in an AI/BI Dashboard and explore with Genie

## 23. Wrap Up & Next Steps
- Real-world Databricks applications and architecture patterns
- Key takeaways from the course
- Where to go next: advanced topics and community resources

## 24. Certification Preparation
- Databricks Certified Data Engineer Associate / Professional
- Databricks Certified Data Analyst Associate
- Databricks Certified Machine Learning Associate / Professional
- Databricks Certified Generative AI Engineer Associate
- Practice questions and exam tips
