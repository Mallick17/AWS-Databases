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

## Redshift Serverless
• Automatically provisions and scales data warehouse underlying capacity
• Run analytics workloads without managing data warehouse infrastructure
• Pay only for what you use (save costs)
• Use cases: Reporting, dashboarding applications, real-time analytics…
