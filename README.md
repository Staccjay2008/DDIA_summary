### DDIA_summary: 

*Terminology: Frontends and Backends*

* **Frontend**: Client-side code, such as web or mobile interfaces, typically handles interactions for a single user and may store some local data.
* **Backend**: Server-side systems that manage requests and data for all users, usually involving:

  * **HTTP/WebSocket APIs**
  * **Stateless application logic**
  * **Persistent data storage** via databases, caches, or message queues (collectively called **data infrastructure**)

### **OLTP vs OLAP, Data Warehousing, and Cloud-Native Architecture**

**1. OLTP vs OLAP:**

* **OLTP (Online Transaction Processing)**: Focuses on real-time, interactive applications like social media, games, and banking. Queries are typically point lookups or small updates.
* **OLAP (Online Analytical Processing)**: Designed for large-scale analytical queries, aggregating over many records. Used in business intelligence and internal analytics.

| Aspect        | OLTP                 | OLAP              |
| ------------- | -------------------- | ----------------- |
| Query Type    | Point queries        | Aggregations      |
| Write Pattern | Create/update/delete | Bulk import (ETL) |
| Users         | End users            | Internal analysts |
| Data Scope    | Current state        | Historical events |
| Data Size     | GBs to TBs           | TBs to PBs        |

**2. Data Warehousing:**

* Introduced to avoid burdening OLTP systems with heavy analytic queries.
* Consolidates data from many operational sources into one analytical database.
* Data is extracted, transformed, and loaded (ETL) into a schema optimized for analysis.

**3. Data Lakes and Lakehouses:**

* **Data Lake**: Raw, unstructured or semi-structured data stored as files (e.g., Parquet, Avro). Suitable for machine learning and advanced analytics.
* **Data Lakehouse**: Hybrid that supports SQL queries and analytics directly on data lake files using tools like Spark SQL, Presto, and Trino.

**4. Systems of Record vs Derived Data Systems:**

* **System of Record**: The source of truth; original data input (e.g., normalized database).
* **Derived Data**: Transformed or aggregated from source data (e.g., cache, ML model, materialized view).

**5. Cloud vs Self-Hosting:**

* **Cloud Services**: Provide scalability, ease of setup, and reduced maintenance. Ideal for variable workloads.
* **Self-Hosting**: Offers greater control, customization, and can be more cost-effective for stable workloads.

| Pros of Cloud         | Cons of Cloud                    |
| --------------------- | -------------------------------- |
| Scalability           | Vendor lock-in                   |
| Fast provisioning     | Less customization               |
| Offloaded maintenance | Limited debugging & transparency |

**6. Cloud-Native Architecture:**

* Emphasizes **separation of storage and compute**.
* Uses **object storage** (e.g., S3) instead of traditional disk for durability and scalability.
* Designed for **multitenancy**, allowing better hardware use across customers.
* Examples include **Snowflake**, **BigQuery**, and **Google Spanner**.

**7. DataOps and Real-Time Analytics:**

* Operational focus is shifting to **DataOps**, emphasizing governance, reliability, and continuous data delivery.
* Streaming and reverse ETL support **real-time insights** and **feedback into operational systems** (e.g., fraud detection, recommendations).

---

Would you like this turned into a presentation slide or visual diagram?
