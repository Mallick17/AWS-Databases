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

### Why is SPICE important?

* It **loads your data into memory** and **compresses** it (In columnar format)
* Data can be refreshed on schedule (e.g., daily)
* Dashboards load much **faster** than querying Redshift or S3 live
* You avoid querying source DBs again and again (Speeds up dashboards by avoiding repeated queries to the data source)
* It’s **built into QuickSight**, no separate install needed
* Automatically scales to millions of rows and thousands of users

> You can think of SPICE as **RAM-optimized storage** that QuickSight uses for speed
> Think of SPICE as an in-memory data cache and processor optimized for dashboards.

### Example:

* You have a 100 MB CSV in S3.
* SPICE loads it into memory, compresses to 30 MB.
* Now, all users view dashboards fast – no repeated queries to S3.

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
| Spice Storage   | 10 GB/user included; \$0.25/GB extra                    |

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

## Real-World Analogy

> Imagine you own a chain of stores. Every night, sales data from all stores is saved in S3.
> You want to:
>
> * Track top-selling products
> * See weekly revenue trends
> * Compare sales by region

QuickSight lets you:

* Connect to S3 data
* Build charts and dashboards
* Auto-refresh and share with your team
  
### Real-World Example

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

## Hands-On: How to Use Amazon QuickSight

We’ll do a **practical walkthrough** using:

* S3 (data source)
* QuickSight
* SPICE (in-memory engine)

<details>
   <summary>Step-by-Step: Set Up QuickSight with S3</summary>

---

## 🔧 Step-by-Step: Set Up QuickSight with S3 (Sample CSV Data)

---

### **Step 1: Prepare Your Data**

Upload a sample CSV to your S3 bucket.
Example CSV: `sales_data.csv`

```csv
Date,Region,Product,Sales
2023-06-01,North,Shampoo,350
2023-06-01,South,Toothpaste,450
2023-06-02,North,Soap,220
...
```

---

### **Step 2: Enable Amazon QuickSight**

1. Go to [Amazon QuickSight Console](https://quicksight.aws.amazon.com/)
2. Click **Sign up** or **Enable QuickSight**
3. Choose:

   * **Enterprise edition** (for SPICE, ML insights, VPC support)
   * Region (e.g., ap-south-1 – Mumbai)
   * Author or Reader role
4. Enable **S3** and **Athena/Glue** permissions during setup

---

### **Step 3: Create a Dataset**

1. On QuickSight, click **Datasets**
2. Click **New Dataset**
3. Choose **S3** as source
4. Enter **S3 manifest file** or **file URL**
   Example:

   ```
   s3://your-bucket-name/sales_data.csv
   ```
5. QuickSight will **import into SPICE** (by default)

---

### **Step 4: Prepare Data (Optional)**

* Rename columns if needed
* Convert data types (e.g., Date column)
* Add calculated fields like:

  ```plaintext
  = ifelse(Sales > 300, "High", "Low")
  ```

---

### **Step 5: Build a Dashboard**

1. Go to **Analyses**
2. Click **New Analysis**
3. Choose your dataset
4. Create visuals:

   * Bar chart: Sales by Region
   * Line chart: Sales over time
   * Pie chart: Sales by Product
5. Add filters (e.g., date range)
6. Add controls (dropdowns, sliders)

---

### **Step 6: Save & Share Dashboard**

* Click **Share** → **Dashboard**
* Share with IAM users/groups or **embed** in apps
* You can schedule refresh of SPICE every day/hour

</details>

---

## When to Use QuickSight

| Need                         | Use QuickSight?          |
| ---------------------------- | ------------------------ |
| Business Dashboards          | ✅ YES                    |
| Ad-hoc SQL Analysis          | ✅ YES                    |
| Embed Dashboards in SaaS App | ✅ YES                    |
| Full Data Warehouse          | ❌ (Use Redshift instead) |
| Just ETL                     | ❌ (Use Glue instead)     |

## Summary Table

| Feature         | Amazon QuickSight                        |
| --------------- | ---------------------------------------- |
| Type            | BI & Data Visualization Tool             |
| Serverless      | Yes                                    |
| Scalable        | Millions of rows/users                 |
| Storage Engine  | SPICE (in-memory)                        |
| Integrated With | S3, Athena, Redshift, RDS, Aurora        |
| Pricing         | Per user (Author) & per session (Reader) |
| Security        | IAM, row-level, VPC, encryption          |
| Embedding       | Web/mobile apps                        |
| ML Support      | Forecasting, anomalies, NLP (Q)        |
| **SPICE Engine**    | In-memory, fast, scalable storage for dashboards   |
| **Integrated With** | S3, RDS, Redshift, Athena, Snowflake               |
| **Visualization**   | Bar, line, pie, tables, heatmaps, KPIs             |
| **Security**        | IAM, row-level, encryption, VPC access             |
| **Smart ML**        | Forecasting, anomaly detection, NLP (QuickSight Q) |
| **Serverless**      | Yes (fully managed)                                |

---

## 🧪 Sample Use Case: Retail Sales Dashboard

**Data Source**: Athena (querying S3)
**Transformations**: via Glue or calculated fields
**Dashboard**:

* KPI cards for daily sales
* Bar chart for region-wise performance
* Forecast chart for next 7 days
* Filters by product category, date, store

---

## 🔗 Official Resource

📎 [Amazon QuickSight Documentation](https://docs.aws.amazon.com/quicksight/)
📎 [Product Page & Pricing](https://aws.amazon.com/quicksight/)

---
