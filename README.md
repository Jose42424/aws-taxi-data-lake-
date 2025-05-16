# 🚖 NYC Yellow Taxi Data Lake on AWS

Build a **serverless, scalable data lake** using **AWS Glue**, **S3**, and **Athena** to query NYC Yellow Taxi trip data efficiently in Parquet format.

---

## 📊 Project Overview

This project demonstrates how to build a modern data engineering pipeline on AWS to:

- Store raw trip data in **Amazon S3**
- Use **AWS Glue Crawlers** to catalog schema metadata
- Query and analyze large datasets using **Amazon Athena** with SQL

---

## 🧱 Architecture

```
NYC Taxi Data (.parquet)
        ↓
     Amazon S3
        ↓
   AWS Glue Crawler
        ↓
   Glue Data Catalog
        ↓
     Amazon Athena
        ↓
       SQL
```

---

## 🧰 Tools Used

| Service        | Purpose                             |
|----------------|-------------------------------------|
| **S3**         | Raw data lake storage               |
| **AWS Glue**   | Metadata catalog & schema inference |
| **Athena**     | Serverless SQL queries              |
| **Parquet**    | Columnar storage format (fast & cheap to scan) |
| **NYC Taxi Data** | Real-world trip dataset from [NYC TLC](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) |

---

## 💡 Sample SQL Query (Athena)

```sql
SELECT 
    DATE(tpep_pickup_datetime) AS trip_day,
    AVG(trip_distance) AS avg_distance,
    COUNT(*) AS trip_count
FROM nyc_taxi_db.nyc_cab_data_joseph
GROUP BY trip_day
ORDER BY trip_day;
```

---

## 📈 Learning Outcomes

- Design a **cost-efficient, serverless data pipeline**
- Ingest and analyze real-world Parquet data at scale
- Use AWS-native services together without provisioning infrastructure

---

## 📁 Project Structure

```
aws-taxi-data-lake/
├── README.md
├── queries/
│   └── sample_analysis.sql
├── screenshots/
│   └── athena-query.png
```

---

## 🚀 Future Enhancements

- Add **scheduled Glue jobs** for automated ETL
- Build a **QuickSight dashboard** for visual analytics
- Deploy via **IaC (Terraform or CDK)**

---

## 🧠 Author

**Joseph** — Data Analyst & Cloud Engineer in training ☁️📊  
Connect on [GitHub](https://github.com/Jose42424)
