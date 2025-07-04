# AWS-Databases
# Amazon QuickSight (BI & Analytics Tool on AWS)
## What is Amazon QuickSight?
**Amazon QuickSight** is a **serverless, cloud-native Business Intelligence (BI) service** that helps you:
* Connect to your data (from S3, RDS, Redshift, Athena, etc.)
* Analyze it using powerful visuals
* Share dashboards with others securely
* Embed analytics into websites or apps
* Use ML features like forecasting and anomaly detection
* Create interactive dashboards
* Visualize and analyze your data
* Generate business insights using ML (machine learning) features

> Think of QuickSight as AWS’s answer to tools like Tableau or Power BI — but with built-in scalability, performance, and AWS-native integrations.

---

## Key Features

| Feature                  | Description                                                       |
| ------------------------ | ----------------------------------------------------------------- |
| **Serverless**           | No need to manage infrastructure – scales automatically           |
| **ML Insights**          | Auto-anomaly detection, forecasting, and natural language queries |
| **Embedded Analytics**   | Embed dashboards into web or mobile apps                          |
| **Scalable**             | Supports thousands of users via SPICE engine                      |
| **Secure & Managed**     | Integrated with IAM, SSO, and row-level security                  |
| **Multi-Source Support** | Connects to S3, Redshift, RDS, Athena, Snowflake, etc.            |
| **Pay-per-Session**      | Pay only when users access dashboards (Reader sessions)           |

---

## Use Cases

1. **Business Analytics**
   Build real-time dashboards from sales, finance, or inventory data.

2. **Embedded BI**
   Integrate QuickSight dashboards directly into web applications.

3. **Self-Service Reporting**
   Allow users (even non-tech users) to explore and analyze data without writing SQL.

4. **Ad-hoc Analysis**
   Quickly run custom reports and visual queries over large datasets.

5. **ML-Driven Insights**
   Forecast trends or automatically detect anomalies using ML Insights.

---

## Compatible AWS & External Services

### **AWS Native Integrations**

QuickSight can connect to the following services **directly**:

| AWS Service             | Purpose                                              |
| ----------------------- | ---------------------------------------------------- |
| **Amazon S3**           | Analyze CSV, JSON, Parquet files stored in S3        |
| **Amazon Athena**       | Query structured data in S3 using SQL                |
| **Amazon Redshift**     | Analyze large-scale structured data warehouse        |
| **Amazon RDS**          | Connect to MySQL, PostgreSQL, Aurora, etc.           |
| **Amazon Aurora**       | Analyze transactional data                           |
| **AWS Glue**            | Use Glue Data Catalog as metadata layer              |
| **Amazon OpenSearch**   | Query data in Elasticsearch clusters                 |
| **Amazon QuickSight Q** | Natural language querying (Ask questions in English) |

### **Third-Party & On-Premise Sources**

* **Snowflake**
* **Teradata**
* **SQL Server**
* **Oracle**
* **MySQL / PostgreSQL**
* **SaaS Apps** like Salesforce, ServiceNow (via connectors)

---

## Architecture Overview

```plaintext
           +-------------------------+
           |    Data Sources (S3,    |
           |    Redshift, Athena,    |
           |    Aurora, RDS, etc.)   |
           +------------+------------+
                        |
                +-------v--------+
                |   SPICE Engine |   <-- Super-fast, in-memory calculation engine
                +-------+--------+
                        |
         +--------------+------------------+
         |        QuickSight Console       |
         |   Dashboards, Charts, Reports   |
         +---------------------------------+
                        |
              +------------------+
              | Embedded Analytics|
              |  via SDK/IFrames  |
              +------------------+
```

---

## What is SPICE Engine?

**SPICE** = **Super-fast, Parallel, In-memory Calculation Engine**

* Stores data in memory (columnar format)
* Speeds up dashboards by avoiding repeated queries to the data source
* Automatically scales to millions of rows and thousands of users

> 🔍 Think of SPICE as an in-memory data cache and processor optimized for dashboards.

---

## Security Features

| Feature                | Description                                     |
| ---------------------- | ----------------------------------------------- |
| **IAM Integration**    | Role-based access to dashboards                 |
| **Row-level Security** | Filter data based on user’s identity            |
| **VPC Connectivity**   | Connect to private data sources securely        |
| **Encryption**         | Data encrypted in transit and at rest using KMS |

---

## Pricing Explained

Amazon QuickSight has **two main pricing models**:

### 1. **Authors**

> People who create dashboards and reports.

| Feature         | Cost                                                    |
| --------------- | ------------------------------------------------------- |
| Monthly Pricing | **\$24/user/month** (or \$18/user/month if annual)      |
| Includes        | Unlimited dashboards, SPICE capacity, scheduled reports |

---

### 2. **Readers**

> People who only view dashboards (cannot create or edit).

| Pricing Model           | Cost                                                                 |
| ----------------------- | -------------------------------------------------------------------- |
| Per Session             | **\$0.30/session**, up to **\$5/month/user** (first 4 sessions free) |
| Includes                | View dashboards, interact with filters, export reports               |
| Embedded Reader Pricing | Custom rates available via API usage                                 |

> You only pay **when a reader accesses the dashboard** — great for scalable apps!

---

## Deployment Options

| Option                    | Description                                                     |
| ------------------------- | --------------------------------------------------------------- |
| **QuickSight Standard**   | Older edition, limited functionality (deprecated for new users) |
| **QuickSight Enterprise** | Full feature set with ML, row-level security, VPC access        |
| **QuickSight Embedded**   | Use SDK to show dashboards inside external applications         |

---

## Smart Features (AI/ML Capabilities)

| Feature               | Description                               |
| --------------------- | ----------------------------------------- |
| **Auto-Narratives**   | Auto-generate summaries and insights      |
| **Anomaly Detection** | Detect unexpected trends or spikes        |
| **Forecasting**       | Predict future trends based on history    |
| **QuickSight Q**      | Ask data questions in plain English (NLP) |

> Example: “What were sales in India last month by category?”

---

## Visualization Types

* Bar, Line, Pie Charts
* KPIs & Gauges
* Pivot Tables
* Geospatial Maps
* Scatter Plots
* Combo Charts
* Heatmaps
* Forecast Lines

---

## Real-World Example

> **Scenario**: A retail company wants a dashboard for regional managers showing:
>
> * Sales by region
> * Top 10 performing stores
> * Forecasted sales for next month
> * Alerts when sales drop 15% below monthly average

**Solution**:

1. Raw sales data is in **Amazon RDS**
2. Use **Amazon Glue** to catalog and transform
3. Load into **SPICE**
4. Build interactive dashboards with alerts in **QuickSight**
5. Embed dashboard in company portal for managers

---

## Summary Table

| Feature         | Amazon QuickSight                        |
| --------------- | ---------------------------------------- |
| Type            | BI & Data Visualization Tool             |
| Serverless      | ✅ Yes                                    |
| Scalable        | ✅ Millions of rows/users                 |
| Storage Engine  | SPICE (in-memory)                        |
| Integrated With | S3, Athena, Redshift, RDS, Aurora        |
| Pricing         | Per user (Author) & per session (Reader) |
| Security        | IAM, row-level, VPC, encryption          |
| Embedding       | ✅ Web/mobile apps                        |
| ML Support      | ✅ Forecasting, anomalies, NLP (Q)        |

---

## 🔗 Official Resource

📎 [Amazon QuickSight Documentation](https://docs.aws.amazon.com/quicksight/)
📎 [Product Page & Pricing](https://aws.amazon.com/quicksight/)
