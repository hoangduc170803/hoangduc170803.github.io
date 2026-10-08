---
layout: page
title: NYC Taxi Pipeline
description: An end-to-end batch and streaming pipeline on Google Cloud
importance: 3
category: work
---

**NYC Taxi Data Pipeline**
Terraform · Apache Airflow · BigQuery · dbt · Apache Spark · Apache Kafka · Apache Flink

An end-to-end pipeline over the New York City taxi trip dataset, built to work through the whole stack
rather than any one piece of it.

- All cloud resources are provisioned with **Terraform**, so the environment is reproducible from scratch.
- An **Apache Airflow** DAG orchestrates ingestion and transformation, loading results into **BigQuery**
  and modelling them with **dbt**.
- **Apache Spark** handles the large-scale batch processing, and **Kafka** with **Flink** adds a real-time
  streaming path alongside it.
