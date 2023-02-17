## Amazon S3 Cross-Region Replication (CRR) and Object Lifecycle & Different Amazon Kinesis Services 

## Cloud Research

S3 CRR

-it automatically copies data between buckets across different Regions with lower-latency. regarding the replication-->bucket/shared prefix /object level (by using S3 object tags)

-if got compliance, low-latency, regional efficiency requirements-->S3 CRR

S3 Lifecycle 

-rules can be added in s3 lifecycle config to ask s3 to transit objects to another s3 storage class 

Amazon S3 Intelligent-Tiering storage class 

-for unpredictable access patterns. designed for cost optimisation by moving data to the most cost-effective access tier automatically when access patterns change 

-objects <128 KB are not eligible 

Amazon Kinesis (Amazon Kinesis Data Streams, Amazon Kinesis Firehose, Amazon Kinesis Data Analytics, Amazon Kinesis Video Streams)

#Amazon Kinesis Data Firehose (https://aws.amazon.com/kinesis/data-firehose/?kinesis-blogs.sort-by=item.additionalFields.createdDate&kinesis-blogs.sort-order=desc)

-a fully-managed service and designed to load streaming data into data lakes, data stores, and analytics services. it can capture, deliver data to s3, http endpoints, redshift etc. 

-can also batch, compress, transform, and encrypt your data streams before loading (minimises storage and increased security)

-easier to operate compared to kinesis data streams, but data firehose has a higher latency 


## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1626656207137083392)
