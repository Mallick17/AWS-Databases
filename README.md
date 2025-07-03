# AWS-Databases
# AWS Redshift
- Redshift is based on PostgreSQL, but it’s not used for OLTP(Online Transaction Processing) that is RDS good for(OLTP).
- Redshift uses OLAP – online analytical processing (analytics and data warehousing).
- Load data once every hour, not every second.
- 10x better performance than other data warehouses, scale to PBs of data.
- Columnar storage of data (instead of row based).
- Massively Parallel Query Execution (MPP), highly available.
- Pay as you go based on the instances provisioned.
- Has a SQL interface for performing the queries.
- BI tools such as AWS Quicksight or Tableau integrate with it.

# **AWS Redshift Serverless – Overview & Workflow Documentation**
## What is Amazon Redshift Serverless?

**Amazon Redshift Serverless** is a fully managed data warehouse solution provided by AWS that:

* **Removes the need to manage infrastructure** like clusters or nodes.
* **Automatically provisions and scales** the resources needed to run your data analytics workloads.
* Allows you to **pay only for the compute and storage you actually use**, which helps you **save costs**.
* Is ideal for workloads with unpredictable or variable usage patterns.

---

## **Key Features**

* 🔄 **Automatic provisioning & scaling**: You don’t need to manually allocate capacity. Redshift Serverless automatically adjusts compute power based on your workload.
* 🧰 **No infrastructure management**: You focus on your queries and data, not hardware or tuning.
* 💸 **Cost-effective**: You are charged only when queries run (based on compute seconds and data scanned).
* 📊 **Use cases**: Reporting, dashboards, business intelligence (BI), real-time data analytics, and ad-hoc querying.

---

## **Step-by-Step Workflow (As Shown in the Image)**

![image](https://github.com/user-attachments/assets/ebab8dd7-56a1-463d-bfa6-4b943cc8766f)

Let’s break down the **Redshift Serverless workflow** step by step:

### 🔹 **Step 1: Enable Redshift Serverless for your AWS account**

* Go to the **AWS Management Console**.
* Navigate to **Amazon Redshift** and choose the **“Serverless” option**.
* Create a **Redshift workgroup** (a logical container for your Serverless warehouse).
* Define permissions, VPC access, and encryption settings if needed.

### 🔹 **Step 2: Connect using Redshift Query Editor or other BI tools**

* Use **Amazon Redshift Query Editor v2**, which is built into the AWS Console, to run queries.
* Alternatively, connect with third-party BI tools like **Tableau, Power BI, Looker, or DBeaver**.
* You can load your datasets using Amazon S3, AWS Glue, or SQL commands.

### 🔹 **Step 3: Redshift Serverless automatically handles compute and scaling**

* When you run a query, Redshift Serverless:

  * Automatically **starts the necessary compute resources**.
  * **Scales up or down** based on the size and complexity of your workload.
  * Shuts down compute resources when not needed (to reduce costs).

### 🔹 **Step 4: Pay only for what you use**

* Billing is based on:

  * **Compute**: Based on Redshift Processing Units (RPUs) used during active querying.
  * **Storage**: Based on how much data you store in your warehouse.
* You do **not pay for idle compute**, which means it's great for spiky or unpredictable workloads.

---

## 🧑‍💻 **Example Use Case: Reporting Dashboard**

Imagine you want to build a weekly sales dashboard:

* ✅ Upload data to S3 or stream via Kinesis.
* ✅ Redshift Serverless ingests and stores that data.
* ✅ You query it from a BI tool or Redshift Query Editor.
* ✅ It runs only when you generate your reports.
* ✅ You’re charged **only during that query time** — no 24/7 charges!

---

## 📎 Benefits Summary

| Benefit              | Description                                             |
| -------------------- | ------------------------------------------------------- |
| 🚫 No Infrastructure | No cluster setup, node management, or capacity planning |
| 📈 Auto Scaling      | Automatically adjusts resources to match query load     |
| 💰 Cost Efficient    | Pay-per-use model helps reduce unused resource costs    |
| ⚙️ Integration       | Easy to connect with tools like S3, Glue, BI dashboards |
| 🔒 Secure            | Supports IAM roles, VPC access, and encryption          |

---

## 🔗 AWS Documentation Links

* [🔗 Amazon Redshift Serverless Overview](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-whatis.html)
* [🔗 Getting Started with Redshift Serverless](https://docs.aws.amazon.com/redshift/latest/mgmt/serverless-getting-started.html)
* [🔗 Pricing for Redshift Serverless](https://aws.amazon.com/redshift/pricing/)

---

