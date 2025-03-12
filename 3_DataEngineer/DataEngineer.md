#### **1. Spark (очень высокий приоритет)**

Apache Spark — основа работы с большими данными.

- **Библиотека**: `pyspark`
- **Что изучить**:
    - RDD, DataFrame, Dataset
    - Spark SQL
    - Оптимизация (Catalyst, Tungsten)
    - PySpark UDF и Pandas UDF
    - Partitioning & Shuffling
    - Работа с Hive

#### **2. Kafka (высокий приоритет)**

Для потоковой обработки данных.

- **Библиотеки**: `confluent-kafka`, `aiokafka`
- **Что изучить**:
    - Продюсеры и консюмеры
    - Топики, партиции, репликация
    - Kafka Streams
    - Интеграция с Spark и Airflow

#### **3. Docker + Kubernetes (высокий приоритет)**

Для разворачивания дата-инфраструктуры.

- **Что изучить**:
    - Dockerfile, Docker Compose
    - Kubernetes (Pod, Deployment, Service, ConfigMap, Helm)
    - CI/CD (GitHub Actions, GitLab CI)

#### **4. Cloud (AWS/GCP/Azure) (высокий приоритет)**

Облачные сервисы для хранения и обработки данных.

- **Что изучить**:
    - S3, GCS, Azure Blob Storage
    - Lambda Functions
    - Managed RDBMS (Aurora, Cloud SQL)
    - Data Pipelines (AWS Glue, GCP Dataflow)

#### **5. DWH (Snowflake/BigQuery/Redshift) (средний приоритет)**

Для построения аналитических систем.

- **Что изучить**:
    - Архитектура
    - Partitioning & Clustering
    - Query Optimization

#### **6. dbt (средний приоритет)**

Инструмент для трансформации данных в DWH.

- **Что изучить**:
    - Модели, источники, макросы
    - Materialized Views

#### **7. REST & gRPC (средний приоритет)**

Для построения API.

- **Что изучить**:
    - FastAPI
    - gRPC (protobuf, unary & streaming RPC)

#### **8. Rust/Scala (низкий приоритет, но полезно)**

Если потребуется высокая производительность или работа с JVM-системами.

- **Что изучить**:
    - Rust (для системного программирования)
    - Scala (для Spark)

Если твоя цель — углубиться в Big Data, сосредоточься на Spark, Kafka, DWH и облаках.  
Если больше DevOps & инфраструктура — Docker/K8s + CI/CD.