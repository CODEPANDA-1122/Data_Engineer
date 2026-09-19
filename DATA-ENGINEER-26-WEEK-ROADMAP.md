# 🗺️ Data Engineering — 26-Week Roadmap

> A complete, week-by-week guide from SQL foundations to portfolio-ready interviews.
> Designed for 5 hours/week, Monday through Saturday, with Sunday off.

---

## 📋 How to read this roadmap

Each week follows one rhythm:

| Mon | Tue | Wed | Thu | Fri | Sat |
|-----|-----|-----|-----|-----|-----|
| Concepts | Core skill | Deep dive | Advanced pattern | Integration | **Prove it** |

Saturday is the **capstone session**: build something you'd put on a résumé,
whiteboard it for a peer, or take a timed mock. No passive reading.

---

## 🏛️ Phase Legend

| Icon | Phase | Weeks | The Big Question It Answers |
|------|-------|-------|-----------------------------|
| 🗃️ | **Foundations** | 1–6 | How do I store, query, and wrangle data? |
| 🏗️ | **Modeling & Cloud** | 7–12 | How do I structure data for analytics at scale? |
| ⚡ | **Big Data** | 13–18 | How do I process millions of records without melting? |
| 🌊 | **Streaming & Design** | 19–26 | How do I ship pipelines that never lie? |

---

## 📊 Master Schedule

| Wk | Phase | Core Topic | AWS Anchor | Sat Deliverable |
|----|-------|-----------|------------|-----------------|
| 1 | 🗃️ | SQL DDL, DML & Joins | RDS (Postgres) | 20 solved queries |
| 2 | 🗃️ | Window Functions & CTEs | RDS (Postgres) | Hard SQL drill set |
| 3 | 🗃️ | Database Internals & Indexing | RDS Performance Insights | Query optimization lab |
| 4 | 🗃️ | Python Engineering & OOP | Cloud9 / Local IDE | JSON parsing script |
| 5 | 🗃️ | NumPy & Pandas Wrangling | DataWrangler | 500k-row CSV cleaning |
| 6 | 🗃️ | File Formats & API Ingestion | S3 (Boto3) | End-to-end API → S3 |
| 7 | 🏗️ | Data Modeling (OLTP vs OLAP) | Schema Conversion Tool | ERD design lab |
| 8 | 🏗️ | Slowly Changing Dimensions | RDS / Redshift | SCD Type 2 pipeline |
| 9 | 🏗️ | Cloud Storage & IAM | S3, IAM | Boto3 IAM automation |
| 10 | 🏗️ | Cloud Data Warehouses | Redshift | 1 GB+ dataset loaded |
| 11 | 🏗️ | Data Transformations with dbt | dbt + Redshift | End-to-end dbt run |
| 12 | 🏗️ | **Capstone 1: Batch Pipeline** | S3 → Redshift → dbt | Portfolio piece 1 |
| 13 | ⚡ | Distributed Computing & Spark | EMR | Local PySpark setup |
| 14 | ⚡ | PySpark Optimization | EMR | PySpark aggregation lab |
| 15 | ⚡ | Lakehouse & Delta Lake | Glue + S3 | Iceberg / Delta comparison |
| 16 | ⚡ | Workflow Orchestration | MWAA (Airflow) | Docker Airflow setup |
| 17 | ⚡ | Airflow + Spark Integration | MWAA + EMR / Glue | End-to-end orchestrated run |
| 18 | ⚡ | Docker & Containerization | ECR, ECS | Containerized full stack |
| 19 | 🌊 | Streaming & Kafka | MSK | Local Kafka cluster lab |
| 20 | 🌊 | Structured Streaming | Kinesis / MSK + EMR | Kafka → Delta Lake stream |
| 21 | 🌊 | Data Quality & CI/CD | CodePipeline / GitHub Actions | CI/CD pipeline built |
| 22 | 🌊 | **Capstone 2: Streaming Pipeline** | MSK → EMR → DynamoDB | Portfolio piece 2 |
| 23 | 🌊 | System Design: Ingestion/Compute | Well-Architected | Whiteboard mock session |
| 24 | 🌊 | System Design: Serving/Security | IAM, Lake Formation | Whiteboard mock session |
| 25 | 🌊 | Optimization & Interview Drills | QuickSight | Mock interview |
| 26 | 🌊 | Portfolio & Final Polish | GitHub, AWS Icons | Final mock interview |

---

## 🗃️ PHASE 1 — FOUNDATIONS (Weeks 1–6)

> *"If you can't explain it to a table, you don't understand it."*
> This phase makes you dangerous with data — in any language, on any engine.

---

### Week 1 — SQL DDL, DML & Joins

> **AWS Anchor:** Amazon RDS (PostgreSQL)
> **Saturday Goal:** 20 solved queries against a real Postgres instance

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | DDL Basics | `CREATE TABLE`, data types (`INTEGER`, `TEXT`, `DATE`, `BOOLEAN`), primary keys. Build a `users` and `orders` table from scratch. |
| **Tue** | Constraints | `NOT NULL`, `UNIQUE`, `CHECK` (e.g. `age >= 0`), `DEFAULT`. Break each one intentionally — read the error message, memorize it. |
| **Wed** | DML & Filtering | `INSERT`, `UPDATE`, `DELETE`, `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`. Load 50 rows, query 5 ways. |
| **Thu** | Inner & Left Joins | `INNER JOIN` (intersection), `LEFT JOIN` (everything left + matches). Predict row counts *before* running. |
| **Fri** | Cross & Self Joins | `CROSS JOIN` (cartesian — know why it's dangerous), self-join (employee → manager hierarchies). |
| **Sat** | LeetCode Practice | 20 queries across the two tables. Time yourself: easy ≤2 min, medium ≤5 min. |

**🔑 Key Concepts:** relational model, cardinality, primary key vs natural key, join semantics
**🛠️ Skills Gained:** write any basic SQL query against a transactional schema
**🔗 Connects To:** Week 2 (window functions assume you can join and filter)

---

### Week 2 — Advanced SQL (Window Functions & CTEs)

> **AWS Anchor:** Amazon RDS (PostgreSQL)
> **Saturday Goal:** Hard SQL drill set (interview-style)

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Window Functions | `ROW_NUMBER`, `RANK`, `DENSE_RANK`. Rank orders per buyer; understand tie behavior. |
| **Tue** | Lead / Lag & Aggregates | `LAG/LEAD` (compare rows), `SUM OVER`, running totals. Compute week-over-week growth in one query. |
| **Wed** | CTEs | `WITH` blocks: name subqueries, layer them, compare readability vs nested. |
| **Thu** | Recursive CTEs | Walk a tree (employee → manager → CEO). Understand the base case + recursion termination. |
| **Fri** | Case & Coalesce | `CASE WHEN` as SQL's `if/else`, `COALESCE` for NULL fallbacks, `NULLIF` for division safety. |
| **Sat** | Hard SQL Drills | 8 tough problems mixing all of the above. Predict output, then run. |

**🔑 Key Concepts:** window function partition/order frames, CTE modularity, NULL semantics
**🛠️ Skills Gained:** write analytical queries interviewers expect from mid-level candidates
**🔗 Connects To:** Week 3 (EXPLAIN tells you *why* your window query is slow)

---

### Week 3 — Database Internals & Indexing

> **AWS Anchor:** Amazon RDS Performance Insights
> **Saturday Goal:** Query optimization lab — fix a slow query end to end

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | B-Trees & Architecture | How Postgres stores data on disk: pages, blocks, heap vs index. Why sequential scan reads everything. |
| **Tue** | Clustered vs Non-Clustered | Clustered = data *is* the index (Postgres heap). Non-clustered = separate pointer tree. When each wins. |
| **Wed** | `EXPLAIN ANALYZE` | Run a slow query, read the plan, add an index, re-run. `SCAN` → `SEARCH` is the victory condition. |
| **Thu** | ACID Properties | `BEGIN/COMMIT/ROLLBACK`. Break a transaction on purpose, roll it back, verify nothing half-wrote. |
| **Fri** | Transaction Isolation | `READ COMMITTED`, `REPEATABLE READ`, `SERIALIZABLE`. Read each other's uncommitted data in a two-session demo. |
| **Sat** | Query Optimization Lab | Take a slow query from the week, diagnose via `EXPLAIN`, add indexes, rewrite. Beat your Friday time by 80%. |

**🔑 Key Concepts:** B-tree mechanics, query planner, ACID, isolation levels, index tradeoffs
**🛠️ Skills Gained:** read a query plan, add the right index, diagnose slow queries
**🔗 Connects To:** Week 5 (pandas `groupby` will feel slow without index awareness)

---

### Week 4 — Python Engineering & OOP

> **AWS Anchor:** AWS Cloud9 or Local IDE
> **Saturday Goal:** JSON parsing script — real data, real validation

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Env Setup (`venv`) | Create a virtual environment, activate it, `pip install`, freeze requirements. Why system Python is a trap. |
| **Tue** | Core Data Structures | `list`, `dict`, `set`, `tuple`. When each is right. Mutable vs immutable. |
| **Wed** | List / Dict Comprehensions | Rewrite three `for` loops as one-liners: map, filter, dict-build. |
| **Thu** | Generators & Iterators | `yield`, `range`, lazy evaluation. Stream a 1M-line file without loading it. |
| **Fri** | OOP Basics | `class`, `__init__`, methods, inheritance. Build a small `Order` class with validation. |
| **Sat** | JSON Parsing Script | Parse a nested JSON API response, validate with `assert`, output a summary. |

**🔑 Key Concepts:** environments, comprehensions, generators, classes, encapsulation
**🛠️ Skills Gained:** write clean, runnable Python scripts with proper structure
**🔗 Connects To:** Week 5 (pandas is built on OOP — you'll read its source now)

---

### Week 5 — NumPy & Pandas Wrangling

> **AWS Anchor:** AWS DataWrangler (awswrangler)
> **Saturday Goal:** Clean a dirty 500k-row CSV — nulls, dtypes, duplicates

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Vectorization Basics | Why `df['col'] * 2` beats a `for` loop. NumPy arrays, broadcasting, vectorized math. |
| **Tue** | Pandas DataFrames | DataFrame creation, `dtypes`, `.head()`, `.info()`, `.describe()`. Read why an `INTEGER` became a `FLOAT`. |
| **Wed** | Filtering & Loc | `df[mask]`, `.loc[]`, `.iloc[]`, boolean masks. The difference is a common interview trap. |
| **Thu** | Groupby & Aggregations | `groupby().agg()`, multi-aggregation, named aggregation. SQL `GROUP BY`, translated. |
| **Fri** | Merges & Joins | `merge(how='inner'/'left'/...)`, indicator, validate. Pandas JOINs — same SQL brain, new syntax. |
| **Sat** | 500k CSV Cleaning Lab | Download a real dataset, clean nulls, fix dtypes, drop dupes, validate. |

**🔑 Key Concepts:** vectorization, dtypes, boolean indexing, groupby-agg, merge semantics
**🛠️ Skills Gained:** wrangle messy data in pandas — the daily work of every DE
**🔗 Connects To:** Week 6 (pandas output goes to file format → API → S3)

---

### Week 6 — File Formats & API Ingestion

> **AWS Anchor:** Amazon S3 (Boto3)
> **Saturday Goal:** End-to-end script: fetch from API → transform → upload to S3

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | API Requests | `requests.get()`, status codes, headers, pagination (`?page=2`), JSON parsing. |
| **Tue** | Parquet vs CSV vs JSON | Columnar vs row-based. Why Parquet wins for analytics (size, speed, dtypes). Read a Parquet file with `pd.read_parquet`. |
| **Wed** | DuckDB Basics | Query CSV/JSON with SQL *without a server*. `SELECT * FROM 'data.csv'`. The bridge between SQL and Python. |
| **Thu** | Boto3 S3 Uploads | `boto3.client('s3').upload_file()`. Buckets, prefixes, keys — upload, list, download. |
| **Fri** | SQLAlchemy Basics | `create_engine`, `read_sql`, ORM vs Core. Write a DataFrame to Postgres in one line. |
| **Sat** | End-to-End API to S3 Script | Fetch paginated data → clean in pandas → save as Parquet → upload to S3. All in one script. |

**🔑 Key Concepts:** REST APIs, file format tradeoffs, boto3, DuckDB, SQLAlchemy
**🛠️ Skills Gained:** ingest data from any source into any destination
**🔗 Connects To:** Week 7 (you have data in S3 — now model it)

---

## 🏗️ PHASE 2 — MODELING & CLOUD (Weeks 7–12)

> *"Modeling is 80% of analytics. Query speed is the other 20%, and it's mostly modeling."*
> This phase turns your data into a structure that survives real questions.

---

### Week 7 — Data Modeling (OLTP vs OLAP)

> **AWS Anchor:** AWS Schema Conversion Tool
> **Saturday Goal:** ERD design lab — sketch, validate, query a star schema

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Normalization (1NF–3NF) | Atomic cells (1NF), no partial dependencies (2NF), no transitive dependencies (3NF). Normalize a messy table by hand. |
| **Tue** | Dimensional Modeling | Fact tables (numbers) vs dimension tables (labels). Kimball's bottom-up approach vs Inmon's top-down. |
| **Wed** | Kimball Methodology | Conformed dimensions, grain statements, bus architecture. Design a mini data mart on paper. |
| **Thu** | Star Schema | One fact, three dimensions, two joins. Build it in SQL. Query revenue per city. |
| **Fri** | Snowflake Schema | Normalize the dimensions further. Compare query cost vs star: more joins, smaller tables. |
| **Sat** | ERD Design Lab | Sketch an e-commerce ERD, implement it, run the revenue query, defend your design choices. |

**🔑 Key Concepts:** OLTP vs OLAP, star vs snowflake, facts vs dimensions, grain, SCD preview
**🛠️ Skills Gained:** design a dimensional model that analysts can actually query
**🔗 Connects To:** Week 8 (dimensions change — here's how to track it)

---

### Week 8 — Slowly Changing Dimensions (SCDs)

> **AWS Anchor:** Amazon RDS / Redshift
> **Saturday Goal:** SCD Type 2 pipeline — expire old row, append new, query as-of

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | SCD Type 0 & 1 | Type 0: never changes (birth date). Type 1: overwrite and forget (typo fix). Know when each is right. |
| **Tue** | SCD Type 2 (History) | Effective dates, surrogate keys, expire + append. The workhorse type — history survives every change. |
| **Wed** | SCD Type 3 & 6 | Type 3: keep previous value in a column. Type 6: combine Type 2 + Type 1 in one row. |
| **Thu** | Surrogate Keys | Why `sk` beats email as a join key: natural keys change, surrogates don't. |
| **Fri** | Snapshot Isolation | Read consistency under concurrent writes. Why `READ COMMITTED` isn't always enough. |
| **Sat** | SCD Type 2 SQL Pipeline | Build a Type 2 dimension, perform a change, verify history + current state both correct. |

**🔑 Key Concepts:** SCD types 0/1/2/3/6, effective dating, surrogate keys, snapshot isolation
**🛠️ Skills Gained:** implement and query slowly changing dimensions
**🔗 Connects To:** Week 9 (IAM protects who can change these dimensions)

---

### Week 9 — Cloud Storage & IAM

> **AWS Anchor:** Amazon S3, IAM
> **Saturday Goal:** Boto3 script that creates a bucket, applies a policy, lists permissions

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | AWS Account Setup | Console, CLI configure, regions, billing alerts. Set a $1 budget alarm — surprise charges end careers. |
| **Tue** | IAM Roles & Policies | JSON policy documents, allow/deny, conditions, ARNs. Read the policy before you trust the role. |
| **Wed** | S3 Buckets & Tiers | Buckets (global names), prefixes (folder illusion), storage tiers (Standard → IA → Glacier). |
| **Thu** | S3 Lifecycle Rules | Auto-transition to Glacier after 30 days, expire after 365. Rules save money on cold data. |
| **Fri** | S3 Encryption (KMS) | SSE-S3, SSE-KMS, SSE-C. Encryption at rest vs in transit. Why both matter. |
| **Sat** | Boto3 IAM Automation | Script: create bucket, attach policy, list ARNs, test access. All from your laptop. |

**🔑 Key Concepts:** buckets, IAM policies, storage tiers, lifecycle, encryption, least privilege
**🛠️ Skills Gained:** secure S3 data and control access programmatically
**🔗 Connects To:** Week 10 (your secured buckets hold the warehouse data)

---

### Week 10 — Cloud Data Warehouses

> **AWS Anchor:** Amazon Redshift
> **Saturday Goal:** Load a 1 GB+ dataset into Redshift and query it

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Redshift Architecture | Nodes, clusters, leader node vs compute node. MPP: how queries parallelize across slices. |
| **Tue** | Compute vs Storage | Redshift spectrum: query S3 data *through* Redshift without loading it. Separating compute from storage. |
| **Wed** | COPY Command from S3 | `COPY table FROM 's3://bucket/data' CREDENTIALS '...' CSV;`. Bulk load, the fastest ingestion path. |
| **Thu** | Distribution Styles | `KEY`, `ALL`, `ROUND-ROBIN`. How data is spread across nodes — wrong choice = slow joins. |
| **Fri** | Sort Keys | `COMPOUND` vs `INTERLEAVED`. Sort keys that prune blocks and skip GB of reading. |
| **Sat** | Load 1 GB+ Dataset | Download a public dataset, COPY into Redshift, run analytical queries, measure performance. |

**🔑 Key Concepts:** MPP, distribution, sort keys, COPY, spectrum
**🛠️ Skills Gained:** deploy and query a cloud data warehouse at scale
**🔗 Connects To:** Week 11 (raw data in Redshift — now transform it with dbt)

---

### Week 11 — Data Transformations with dbt

> **AWS Anchor:** dbt Core + Redshift
> **Saturday Goal:** End-to-end dbt run: staging → marts → tests → docs

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | dbt Setup & Profiles | `dbt init`, `profiles.yml`, warehouse connection. Run `dbt debug`. |
| **Tue** | Staging Models | `stg_` prefix, one model per source table, renames, casts, SQL tests. |
| **Wed** | Mart Models & Refs | `ref()` and `source()` — dbt's dependency graph. Build a revenue mart from staging models. |
| **Thu** | dbt Tests | `unique`, `not_null`, `relationships`, `accepted_values`. Break the data, watch tests fail. |
| **Fri** | dbt Docs | `dbt docs generate`, `dbt docs serve`, lineage diagrams. Every model documented with one line. |
| **Sat** | End-to-End dbt Run | `dbt run` → `dbt test` → `dbt docs generate`. Whole pipeline green, docs live, lineage mapped. |

**🔑 Key Concepts:** models, refs, sources, tests, docs, the dbt DAG
**🛠️ Skills Gained:** transform warehouse data with version-controlled SQL
**🔗 Connects To:** Week 12 (your dbt models are the foundation of Capstone 1)

---

### Week 12 — ⭐ Capstone 1: Batch Pipeline

> **AWS Anchor:** S3 → Redshift → dbt
> **Saturday Goal:** Portfolio piece 1 merged + README peer-tested

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Architecture Planning | Draw the pipeline: where does data come from, where does it land, who consumes it? |
| **Tue** | Python Extraction | Write a script that pulls from an API or file, writes Parquet to S3. |
| **Wed** | S3 Staging | Land the Parquet in S3 with a clean prefix structure: `year=2024/month=01/`. |
| **Thu** | Redshift Ingestion | `COPY` from S3 into a staging table. Verify row counts, check dtypes. |
| **Fri** | dbt Transformation | Build staging → marts → tests. Every metric has an owner. |
| **Sat** | Documentation & GitHub | `dbt docs`, README someone else can rerun, push to GitHub. Peer-test it. |

**🔑 Key Concepts:** end-to-end batch pipeline, idempotent loads, documentation as code
**🛠️ Skills Gained:** ship a portfolio-grade batch pipeline from scratch
**🔗 Connects To:** Week 13 (batch is solved — now scale to billions of rows)

---

## ⚡ PHASE 3 — BIG DATA (Weeks 13–18)

> *"Pandas broke? Good. Now think in clusters."*
> This phase teaches you to process data that doesn't fit on one machine.

---

### Week 13 — Distributed Computing & Spark

> **AWS Anchor:** Amazon EMR
> **Saturday Goal:** Local PySpark setup — your first Spark job on your laptop

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Hadoop vs Spark | MapReduce: disk-heavy, multi-pass. Spark: in-memory, lazy, one platform. Why Spark won. |
| **Tue** | Driver / Executor Architecture | Driver plans, executors run tasks, cluster manager allocates. Know the roles. |
| **Wed** | RDDs vs DataFrames | RDDs: low-level, typed, no optimizer. DataFrames: structured, Catalyzed, the future. Use DataFrames. |
| **Thu** | Lazy Evaluation | Transformations build a DAG; *actions* execute. Why `.count()` is where the work starts. |
| **Fri** | Spark UI Navigation | Open the UI, find stages, tasks, shuffle reads, spilled bytes. Read it top to bottom. |
| **Sat** | Local PySpark Setup | `pip install pyspark`, run a word count, rerun your pandas job as a Spark job. |

**🔑 Key Concepts:** distributed computing, DAG execution, lazy evaluation, Spark UI
**🛠️ Skills Gained:** understand and run Spark, read its UI
**🔗 Connects To:** Week 14 (now that it runs, make it fast)

---

### Week 14 — PySpark Optimization

> **AWS Anchor:** Amazon EMR
> **Saturday Goal:** Diagnose a slow stage, identify skew, apply broadcast fix, compare stage counts

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Narrow vs Wide Transformations | `map`/`filter` (narrow, no shuffle) vs `groupby`/`join` (wide, shuffle). Know which is which. |
| **Tue** | Shuffling & Partitioning | What happens during a shuffle: spill, sort, redistribute. `repartition()` vs `coalesce()`. |
| **Wed** | Coalesce vs Repartition | `coalesce()` — narrow, no shuffle, can create skew. `repartition()` — even spread, full shuffle. |
| **Thu** | Caching & Persist | `.cache()`, `.persist(MEMORY_AND_DISK)`. Cache only what gets reused twice — cache everything else is a memory leak. |
| **Fri** | Handling Data Skew | One giant task = skew. Salting: add a random prefix to keys, distribute the work. |
| **Sat** | PySpark Aggregation Lab | Run aggregations, find the slow stage, diagnose skew, apply salting, compare stage counts. |

**🔑 Key Concepts:** shuffle, partitioning, caching, skew, broadcast, salting
**🛠️ Skills Gained:** diagnose and fix slow Spark jobs — the senior DE differentiator
**🔗 Connects To:** Week 15 (when Spark hits the right scale, you need a lakehouse)

---

### Week 15 — Lakehouse & Delta Lake

> **AWS Anchor:** AWS Glue + S3
> **Saturday Goal:** Compare Iceberg vs Delta on the same dataset

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Data Lakehouse Concepts | Lake (raw files) + Warehouse (structured queries) = lakehouse. One system, both strengths. |
| **Tue** | Parquet Metadata | Schema, row groups, column chunks, statistics. Why the format knows about your data. |
| **Wed** | Delta Lake ACID | Transactions, atomic commits, `_delta_log`. Crash a write, verify consistency. |
| **Thu** | MERGE / Upserts | `MERGE INTO target USING source ON key WHEN MATCHED THEN UPDATE`. The pipeline's idempotent weapon. |
| **Fri** | Time Travel | `SELECT * FROM table VERSION AS OF 5`. Query any past snapshot. Rollbacks without backups. |
| **Sat** | Iceberg / Delta Comparison | Side-by-side: format, engines, features, maturity. Pick one and defend it. |

**🔑 Key Concepts:** lakehouse, ACID on files, MERGE, time travel, format choice
**🛠️ Skills Gained:** manage data at rest with modern table formats
**🔗 Connects To:** Week 16 (table data needs orchestration now)

---

### Week 16 — Workflow Orchestration

> **AWS Anchor:** Amazon MWAA (Airflow)
> **Saturday Goal:** Local Docker Airflow — DAGs running on your machine

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | DAGs & Operators | `DAG`, `@task`, `BashOperator`, `PythonOperator`. A DAG is a recipe, operators are ingredients. |
| **Tue** | Tasks & Dependencies | `>>` operator, upstream/downstream. One DAG, many tasks, clear dependencies. |
| **Wed** | XComs | Pass small data between tasks: `ti.xcom_push/pull`. Paths, not payloads — keep it light. |
| **Thu** | Airflow Sensors | Wait for a file, a table, an API response. Polling vs deferrable — know the tradeoff. |
| **Fri** | Catchup & Backfilling | `catchup=True` on first deploy = avalanche. Backfill one missed week, deliberately. |
| **Sat** | Local Docker Airflow Setup | `docker-compose up` Airflow, open UI, trigger your DAG, watch it run. |

**🔑 Key Concepts:** DAGs, tasks, XComs, sensors, catchup, backfill
**🛠️ Skills Gained:** orchestrate any pipeline as a DAG
**🔗 Connects To:** Week 17 (your DAG now needs Spark inside it)

---

### Week 17 — Airflow + Spark Integration

> **AWS Anchor:** MWAA + EMR / Glue
> **Saturday Goal:** End-to-end orchestrated run: Airflow triggers Spark, monitors, recovers

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | External Triggers | REST API, `TriggerDagRunOperator`, event-based triggers. Start a DAG from another system. |
| **Tue** | SparkSubmitOperator | Submit a PySpark job from Airflow, pass parameters, read return code. |
| **Wed** | Secrets Management | Connections, variables, AWS Secrets Manager backend. Never hardcode keys — that's a breach headline. |
| **Thu** | Failure Alerting | Email, Slack, PagerDuty. SLA misses, task failures, DAG runs. Alerts that reach a human. |
| **Fri** | Idempotency | Rerun the DAG: same input, same output, no duplicates. The test of every production pipeline. |
| **Sat** | End-to-End Orchestrated Run | Airflow → EMR → S3 → dbt → alert. Green. Push to GitHub. Write a one-paragraph README. |

**🔑 Key Concepts:** orchestration, Spark integration, secrets, alerting, idempotency
**🛠️ Skills Gained:** ship a production orchestration stack
**🔗 Connects To:** Week 18 (the whole stack needs to run somewhere reliable)

---

### Week 18 — Docker & Containerization

> **AWS Anchor:** Amazon ECR, ECS
> **Saturday Goal:** Containerize your full local stack — one `docker compose up` does everything

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Docker Basics | Images, containers, `docker run`, `docker ps`, `docker logs`. Run your first container. |
| **Tue** | Dockerfiles | `FROM`, `COPY`, `RUN`, `CMD`, `EXPOSE`. Build an image for a Python script. |
| **Wed** | Multi-Stage Builds | Build stage (compilers, tools) → runtime stage (slim, no build deps). Half the image size, half the CVEs. |
| **Thu** | Docker Compose | `docker-compose.yml`: db + job + volumes. Multi-container local dev. |
| **Fri** | Networking & Volumes | Bridge networks, named volumes, host mounts. Why data vanishes without volumes. |
| **Sat** | Containerize Full Local Stack | Airflow + Postgres + Spark local — all in Compose. `docker compose up` = working pipeline. |

**🔑 Key Concepts:** images, containers, Dockerfiles, Compose, volumes, networking
**🛠️ Skills Gained:** package and run any pipeline in a container
**🔗 Connects To:** Week 19 (containers are the local proxy for managed streaming)

---

## 🌊 PHASE 4 — STREAMING & DESIGN (Weeks 19–26)

> *"Streaming is easy. Exactly-once is a research paper; idempotency is a practice."*
> The capstone phase: streaming systems, design interviews, and your portfolio.

---

### Week 19 — Streaming & Kafka

> **AWS Anchor:** Amazon MSK
> **Saturday Goal:** Local Kafka cluster, produce 100 events, consume, kill, restart, lose nothing

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Streaming vs Batch | Batch = all-or-nothing, latency in hours. Streaming = continuous, latency in seconds. Tradeoffs. |
| **Tue** | Kafka Topics & Partitions | Topics (named streams), partitions (parallelism), offsets (position). How a topic becomes a timeline. |
| **Wed** | Producers & Consumers | `produce()` to a topic, `consume()` from a group. The two ends of every stream. |
| **Thu** | Consumer Groups | Multiple consumers, one topic, partitions divided. Rebalance when someone joins or leaves. |
| **Fri** | Offsets & Retention | Offset = your bookmark in the log. Retention = how long the log keeps history (days, size). |
| **Sat** | Local Kafka Cluster Lab | Docker Kafka + Zookeeper, produce 100 events, consume as group of two, kill consumer, restart, verify nothing lost. |

**🔑 Key Concepts:** topics, partitions, offsets, consumer groups, retention, rebalancing
**🛠️ Skills Gained:** understand and run Kafka, explain consumer group mechanics
**🔗 Connects To:** Week 20 (Kafka feeds the stream processor)

---

### Week 20 — Structured Streaming

> **AWS Anchor:** Amazon Kinesis / MSK + EMR
> **Saturday Goal:** Kafka → Delta Lake stream, watermark, kill-restart, verify identical sink state

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Micro-Batching | Structured Streaming = micro-batches. Micro-batch vs continuous — know the tradeoff. |
| **Tue** | Source & Sink Configs | Read from Kafka, write to Delta/S3/Parquet. Schema evolution, mode (`append`/`update`/`complete`). |
| **Wed** | Sliding Windows | 10-minute tumbling windows vs 10-minute sliding windows (every 5 minutes). When overlap matters. |
| **Thu** | Watermarking | "Late data is a business decision." Set a watermark, late events get dropped, others arrive. |
| **Fri** | Checkpointing | `checkpointLocation` = recovery. Kill mid-batch, restart, verify identical state. |
| **Sat** | Kafka → Delta Lake Stream | Stream from Kafka, apply watermark, write to Delta, kill-restart, prove no data loss. |

**🔑 Key Concepts:** micro-batch, windows, watermark, checkpointing, exactly-once practice
**🛠️ Skills Gained:** build a lossless streaming pipeline
**🔗 Connects To:** Week 21 (the stream needs quality checks and CI/CD)

---

### Week 21 — Data Quality & CI/CD

> **AWS Anchor:** AWS CodePipeline / GitHub Actions
> **Saturday Goal:** CI/CD pipeline: lint → test → deploy — all automated on push

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Great Expectations Basics | `expect_column_values_to_be_between`, `expect_table_row_count_to_be_between`. Suites, validations, checkpoints. |
| **Tue** | Pytest for Pipelines | Test your transform functions, your dbt models, your Spark jobs. One test per pure function. |
| **Wed** | GitHub Actions YAML | `on: push`, `jobs:`, `steps:`. Write a workflow that runs on every PR. |
| **Thu** | Linting (Flake8 / Black / Ruff) | Style checks, type hints, unused imports. One command, zero arguments ever again. |
| **Fri** | Automated Deployments | Push → lint → test → dbt run → deploy. Green on PR, red means stop. |
| **Sat** | CI/CD Pipeline Integration | Full pipeline: GitHub Actions → dbt build → Great Expectations → deploy. All green. Screenshot it. |

**🔑 Key Concepts:** data quality suites, CI/CD, linters, automated deploys
**🛠️ Skills Gained:** ship code and data pipelines with automated quality gates
**🔗 Connects To:** Week 22 (your CI/CD pipeline now hosts the capstone)

---

### Week 22 — ⭐ Capstone 2: Streaming Pipeline

> **AWS Anchor:** MSK → EMR → DynamoDB
> **Saturday Goal:** Portfolio piece 2; whiteboard it from memory

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Architecture Planning | Draw: Kafka → Spark Streaming → Delta Lake → DynamoDB. Label every component. |
| **Tue** | Producer Setup | Write a producer that sends events to a Kafka topic. Heartbeats, real data, both. |
| **Wed** | Streaming Job | Spark Structured Streaming consuming from Kafka, applying watermark, writing to Delta. |
| **Thu** | Target Database Setup | DynamoDB table provisioned or on-demand? Read capacity units, partition keys. |
| **Fri** | Integration | End-to-end: produce → stream → DynamoDB. Verify counts match source. |
| **Sat** | README & Diagrams | Architecture diagram, data flow, failure recovery, README someone else can rerun. |

**🔑 Key Concepts:** end-to-end streaming, production integration, documentation
**🛠️ Skills Gained:** ship a streaming pipeline portfolio piece
**🔗 Connects To:** Week 23 (interviews will ask you to design these from scratch)

---

### Week 23 — System Design: Ingestion/Compute

> **AWS Anchor:** AWS Well-Architected Framework
> **Saturday Goal:** Whiteboard mock session — time-boxed, peer-reviewed

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Throughput Estimation | 1M events/day = ? messages/sec = ? storage/month. Practice with real numbers. |
| **Tue** | Storage Sizing | GB/day × retention = total. Compress, tier, lifecycle — every byte has a cost. |
| **Wed** | DB Selection (SQL/NoSQL) | Structured + relational = Postgres. Document + scale = DynamoDB. Time-series = Timestream. Choose. |
| **Thu** | Fault Tolerance | Multi-AZ, retries with backoff, idempotent consumers, dead letter queues. |
| **Fri** | Idempotent Design | Redelivery happens. Design for it from the start: keyed writes, dedupe on IDs. |
| **Sat** | Whiteboard Mock Session | 30 minutes: design an ingestion pipeline on a whiteboard. Peer review. Repeat. |

**🔑 Key Concepts:** capacity planning, DB selection, fault tolerance, idempotency
**🛠️ Skills Gained:** design ingestion systems under constraint
**🔗 Connects To:** Week 24 (now the serving and security layer)

---

### Week 24 — System Design: Serving & Security

> **AWS Anchor:** AWS IAM, Lake Formation
> **Saturday Goal:** Second whiteboard mock — now with security and serving

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Data Mesh Concepts | Domain ownership, data as a product, self-serve platforms. Decentralize deliberately. |
| **Tue** | Data Lineage | Column-level: where does this metric come from? Track it in code, not Confluence. |
| **Wed** | RBAC & Governance | Roles, policies, row-level security. `GRANT SELECT ON table TO analyst_role`. |
| **Thu** | Data Masking / PII | Mask emails, tokenize PII, encryption at rest. GDPR-shaped thinking. |
| **Fri** | Query Latency Optimization | Materialized views, query caching, sort keys, partition pruning. |
| **Sat** | Whiteboard Mock Session | Design a full system: ingestion → storage → serving → security. Time-boxed, peer-reviewed. |

**🔑 Key Concepts:** data mesh, lineage, RBAC, PII masking, latency optimization
**🛠️ Skills Gained:** design end-to-end systems with security as a feature
**🔗 Connects To:** Week 25 (interview drills sharpen everything)

---

### Week 25 — Optimization & Interview Drills

> **AWS Anchor:** Amazon QuickSight
> **Saturday Goal:** Mock interview — technical screen, 60 minutes

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Timed SQL Tests | 3 SQL problems in 25 minutes: join + window + subquery. Time every attempt. |
| **Tue** | Timed Python Tests | 3 Python problems in 25 minutes: pandas, comprehension, generator. |
| **Wed** | Spark Edge Cases | Skew, shuffle, caching, AQE — the questions that separate offers. |
| **Thu** | Distributed Troubleshooting | Given a slow job UI screenshot, diagnose in 10 minutes. |
| **Fri** | Behavioral Questions | "Tell me about a pipeline failure." STAR format: Situation, Task, Action, Result. |
| **Sat** | Mock Interview | Full technical screen with a peer. 60 minutes. Record it. Review it. Repeat. |

**🔑 Key Concepts:** timed recall, troubleshooting patterns, behavioral framing
**🛠️ Skills Gained:** interview under pressure, articulate your experience
**🔗 Connects To:** Week 26 (polish, apply, repeat)

---

### Week 26 — Portfolio & Final Polish

> **AWS Anchor:** GitHub, AWS Architecture Icons
> **Saturday Goal:** Final mock interview + job applications started

| Day | Focus | What You Actually Do |
|-----|-------|---------------------|
| **Mon** | Résumé CAR Framework | **C**hallenge → **A**ction → **R**esult. One bullet per project: scale, tools, outcome. |
| **Tue** | GitHub Repos Cleanup | README, architecture diagram, clean history, `.gitignore`. Every repo portfolio-ready. |
| **Wed** | Architecture Diagrams | Draw all capstones with AWS icons. Use `diagrams-as-code` or Lucidchart. |
| **Thu** | Write Blog / Post | "How I built a streaming pipeline in 20 minutes." Blog = proof of understanding. |
| **Fri** | Job Applications | 3 applications per day. Track in a sheet: company, role, date, status. |
| **Sat** | Final Mock Interview | Last mock interview before the push. You are ready. |

**🔑 Key Concepts:** portfolio, storytelling, application strategy
**🛠️ Skills Gained:** present yourself as a data engineer
**🔗 Connects To:** Nothing. You're done. Go get the job. 🎓

---

## 📈 Skills Progression Map

```
Week  1 ┃🗃️ SQL basics
Week  6 ┃🗃️🛠️ API ingestion complete
      ↓
Week  7 ┃🏗️ Modeling
Week 12 ┃🏗️⭐ Batch pipeline complete
      ↓
Week 13 ┃⚡ Spark
Week 18 ┃⚡⭐ Docker stack complete
      ↓
Week 19 ┃🌊 Streaming
Week 22 ┃🌊⭐ Streaming capstone complete
      ↓
Week 23 ┃🌊 System design
Week 26 ┃🌊🎓 Portfolio ready
```

---

## 🎯 Weekly Rhythm Cheat Sheet

```
Monday    Learn concepts, read docs, draw on paper
Tuesday   Core skill practice, hands-on lab
Wednesday  Deep dive, read about it, trace it
Thursday  Advanced pattern, build with it
Friday    Integration day, connect two things
Saturday  Prove it: build, demo, test, or whiteboard
Sunday    REST. Protect it.
```

---

## ⚠️ Rules of the Road

1. **5 hours/week, Mon–Sat.** Sunday is sacred. Burnout kills more careers than slow progress.
2. **Friday rule: demo-or-it-didn't-happen.** If you can't screen-share your deliverable, it didn't happen.
3. **Status: `Not Started` → `In Progress` → `Done`.** Flip to Done only when the deliverable exists — not when reading finished.
4. **Owner: who drove this week.** Swap driver/navigator every 45 minutes.
5. **If stuck > 30 minutes on a concept**, move to the next day and come back later. Momentum matters more than perfection.

---

## 📦 What's Covered vs What's Not

**In scope (this roadmap):**
SQL → Pandas → dbt → Spark → Airflow → Kafka → Docker → Streaming → System Design → Interview Prep

**Explicitly cut (with reasons):**
- Redshift deep-admin — needs AWS account; Athena + Postgres concepts transfer
- boto3 / DuckDB / SQLAlchemy hands-on — needs accounts or engines not in-page
- Kubernetes / EKS / GKE — Docker Compose is enough to get hired
- Luigi / Prefect — Airflow is the interview answer
- MLOps / ML math — comes after this plan
- pytest suites — dbt tests carry the testing mindset (per plan)

---

*Source: `data-engineer-24-week-plan.xlsx` · 26 weeks · Pair-based · CachyOS-first where terminal skills apply*
