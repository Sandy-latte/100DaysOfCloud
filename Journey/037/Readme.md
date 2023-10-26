## Cloud Research - AWS data related services: S3 and Glue Catalog 

✍️ S3 

-storage for the Internet. it gives developers access to highly scalable, fast, and inexpensive data infrastructure. aims to max benefits for developers 

-object storage service for structured and unstructured data and the storage service of choice to build a data lake. 11 9s durability 

✍️ AWS Glue 

-fully managed ETL

-aws glue data catalog is your persistent metadata store. it's a managed service that lets u store, annotate, and share metadata in the aws cloud in the same way u would in an apache hive metastore 

-aws glue also lets u set up 'crawlers' that can scan data in all kinds of repositories, classify it, extract schema info from it, and store the metadata automatically in the aws glue data catalog. the aws glue data catalog can then be used to guide ETL operations 

-crawlers use 'classifiers', a classifier reads the data in a data store.  if it recognises the format of the data, it generates a schema. the classifier also returns a certainty number to indicate how certain the format recognition was 

✍️ aws services used for 'data movement' (amazon kinesis, API Gateway) 

✍️ aws services for 'data processing' (Apache Hadoop, EMR, glue jobs, lambda, kinesis analytics, redshift)

-apache hadoop on aws https://aws.amazon.com/tw/emr/details/hadoop/what-is-hadoop/: instead of using one large computer to store and process the data, Hadoop allows clustering multiple computers to analyse massive datasets in parallel more quickly 

