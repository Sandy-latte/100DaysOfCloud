## Cloud Research - AWS data related services: S3 and Glue Catalog 

##S3 (Simple Storage Service)

-storage for the Internet. It's designed to make web-scale computing easier for developers. it gives developers access to highly scalable, fast, and inexpensive data infrastructure. it aims to max benefits for developers 

-object storage service for structured and unstructured data and the storage service of choice to build a data lake. 11 9s durability 

S3 storage classes

-S3 standard-the default storage class 

-reduced redundancy-reduced redundancy storage (RRS) storage class is designed for noncritical, reproducible data that can be stored with less redundancy than the s3 standard storage class

-the s3 standard-IA and S3 one zone-IA storage classes are designed for long-lived and infrequently accessed data. amazon s3 does charge a retrieval fee for these objects, so they're most suitable for infrequently accesssed data 

AWS Glue 

-fully managed ETL (extract, transform, and load) service that makes it simple and cost-effective to categorise ur data, clean it, enrich it, and move it reiably between various data stores and data streams. glue is serverless, so there's no infrastructure to set up or manage 

-aws glue data catalog is your persistent metadata store. it's a managed service that lets u store, annotate, and share metadata in the aws cloud in the same way u would in an apache hive metastore 

-aws glue also lets u set up 'crawlers' that can scan data in all kinds of repositories, classify it, extract schema info from it, and store the metadata automatically in the aws glue data catalog. the aws glue data catalog can then be used to guide ETL operations 

-crawlers use 'classifiers', a classifier reads the data in a data store.  if it recognises the format of the data, it generates a schema. the classifier also returns a certainty number to indicate how certain the format recognition was 

aws services used for 'data movement' (amazon kinesis, API Gateway)

-data movement: data lakes allow u to import any amount if data that can come in real-time. data is collected from multiple sources, and moved into the data lake in its original format. the process allows u to scale to data of any size, while saving time of defining data structures, schema, and transformations

-amazon kinesis https://aws.amazon.com/tw/kinesis/ makes it easy to collect, process, and analyse real-time, streaming data so u can get timely insights. for data ingestion, there's amazon kinesis data streams, kinesis video streams , and kinesis data firhose 

amazon API Gateway https://aws.amazon.com/tw/api-gateway/

-fully managed service that makes it easy to create, publish, and maintain secure APIs at scale. APIs are the front door to backend appications and services. API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of API calls, including traffic management, CORS support, authorisation and access control, throtting, monitoring, and API version management 

aws services for 'data processing' (Apache Hadoop, EMR, glue jobs, lambda, kinesis analytics, redshift)

-apache hadoop on aws https://aws.amazon.com/tw/emr/details/hadoop/what-is-hadoop/: an open source framework that is used to efficiently store and process large datasets ranging in size from gigabytes to petabytes of data. instead of using one large computer to store and process the data, Hadoop allows clustering multiple computers to analyse massive datasets in parallel more quickly 

Amazon EMR

-a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark, on AWS to process and analyse vast amounts of data. by using these frameworks and related open-source projects, such as Apache Hive and Apache Pig, u can process data for analytics purposes and BI workloads. additionally, u can use amazon EMR to transform and move large amounts of data into and out of other AWS data stores and databases 

-with a serverless Aamazon EMR option 

AWS Glue DataBrew https://aws.amazon.com/tw/glue/features/databrew/

-a new visual data preparation tool that makes it easy for data analysts and scientists to clean and normalise data to prepare it for analytics and machine learning. u can choose from over 250 pre-built transformations to automate data preparation tasks, without writing any code 

-u can automate filtering anomalies, converting data to standard formats and correcting invalid values

aws glue jobs 

-a job's the business logic that performs the extract, transform, and load work in aws glue

athena

-interactive query service that makes it easy to analyse data directly in s3 using standard sql

redshift 雲端資料倉儲的最高價格效能比 https://aws.amazon.com/tw/redshift/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc

-makes it simple and cost effective to run high performance queries on petabytes of structured data so that u can build powerful reports and dashboards using ur existing BI tools 

aws lake formation

-makes it easier for u to build, secure, and manage data lakes 

-it helps u: register the s3 buckets and paths where your data lake will reside, orchestrate data flows that ingest, cleanse, transform, and organise the raw data, and create and manage a Data Catalog containing metadata about data sources and data in the data lake, define granular data access policies to the metadata and data, and through a grant/revoke permissions model 

