(On leave from 6th-12th Feb, will use 13th, 14th to catch up the due progress and documentation over the past few days) 

## Cloud Research
Databases on AWS(Amazon Aurora, Amazon RDS Proxy, Amazon DynamoDB)

-purpose-built on AWS-_>each AWS database service is built for a specific use case/set of use cases 

Amazon Aurora 

-a fully managed relational database engine which's compatobel with MySQL and PostgreSQL

-enterprise=level database-->deliver up to 5 times the throughput of MySQL and up to 3 times the throughput of PostgreSQL without requiring changes to most of your applications

-includes a high-performance storage subsystem. its MySQL/PostgreSQL-compatible database engines are customised to make the most of the fast, distributed storage. the underlying storage grows automatically as needed. an aurora cluster can grow up to a max size of 128tebibytes (TiB)
aurora automates and standardises also database clustering and replication (which are typically among the most challenging aspects of database configuration and admin)

-part of amazon RDS. amazon RDS is a web service that makes it easier to set up, operate, and scale a relational database in the cloud

-aurora serverless v2 (https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/aurora-serverless-v2.html)-->an on-demand, automatic scaling configuration for aurora. it helps automate the processes of monitoring workload & adjusting capacity for your databases. capacity is automatically adjusted based on application demand-->you're charged for the resources that your db clusters consume-->save budget 

-very VALUABLE for multitenant databases, distributeed databses, development and test systems, and environments with highly unpredictable workloads

-https://aws.amazon.com/rds/aurora/getting-started/

Amazon RDS proxy (https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/rds-proxy.html)

-with amazon rds proxy, your applications can pool and share database connections to improve their ability to scale. rds proxy enables applications more resilient to database failures by automatically connecting to a standby DB instance, while preserving application connections. you can also enforce AWS IAM  authentication for databases, and securely store credentials in AWS Secrets Manager 

-able to handle unpredictable surges in database traffic such as oversubscribing connections/creating connections at a fast rate-->rds proxy establishes a database connection pool and reuses connections in this pool without the memory and CPU overhead of opening a new database connection each time. to protect the database against oversubscription, you can control the number of database connections that are created 

-rds proxy queues/throttles application connections that can't be served instantly from the pool of connections. altho latency might go up, your application can continue to scale without abruptly failing/overwhelming the database 

Amazon DynamoDB

-with DynamoDB, you can create database tables that can store and retrieve virtually any amount of data and server virtually any level of request traffic 

-uses alternatate models for data management like key-valuee pairs/document storage 

-tables, items, and attributes are the core components that you work with. 
table's a collection of items, and each item's a collection of attributes. DynamoDB uses primary keys to uniquely identify each item in a table, and secondary indexes to provide more querying flexibility

-https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html

-aws dynamodb cheat sheet: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/CheatSheet.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/WorkingWithTables.html
https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html


## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1625184537067065344)
