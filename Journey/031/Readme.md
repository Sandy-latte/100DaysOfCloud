Processing data in data lakes

## Cloud Research

columnar data format and athena partitioning 

-apache parquet and ORC are columnar storage formats that are optimised for fast retrieval of data and used in aws analytical applications 

-by partitioning your data, u can restrict the amount of data Athena scans by each query, thus improving performance and reducing cost 

aws glue jobs 

-an aws glue job encapsulates a script that connects to ur source data, process it, and then writes it out to your data target. typically, a job runs ETL scripts. aws glue provides a set of built-in transforms that u can use to process ur data. u can call these transforms from ur ETL script. ur data passes from transform to transform in a data structure called a DynamicFrame, which is an extension to an Apache Spark SQL DataFrame. the DynamicFrame contains ur data, and u refernce its scheme to process your data 

-DataFrames are powerful and widely used, but they have limitations with respect to ETL operations. most significantly, they require a scheme to be specified before any data is loaded 
