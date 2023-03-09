Exam notes review 1 [scenario and notes]
## Cloud Research

-Scheduled scaling allows you to create your own scaling schedule and sets the min, max, and desired sizes to what is specified by the scheduled action at the time specified by the scheduled action

-Amazon API Gateway is a fully managed service that allows you to publish, maintain, monitor, and secure APIs at any scale. It offers options to create RESTful APIs, HTTP APIs and REST APIs, also an option to create WebSocket APIs

HTTP API: optimised for building APIs that proxy to AWS Lambda functions/HTTP backends-->enable for serverless workloads. No API management functionality 

REST API: offers API proxy functionality and API management features in a single solution. offers API management features, such as usage plans, API keys, publishing, and monetizing APIs

WebSocket API: maintain a persistent connection between connected clients to enable real-time message comm. With WebSocket APIs in API Gateway, you can define backend integrations with AWS Lambda functions/Kinesis /any HTTP endpoint to be invoked when msgs are received from the connected clients 

-Amazon FSx for Lustre: enable cost-effectively running high performance file system. It is used for workloads such as ML, high-performance computing (HPC), video processing, and financial modeling. it integrates with S3, enable processing data sets with the Lustre file system. When linked to an S3 bucket, an FSx for Lustre file sys presents S3 objects as files and allows you to write changed data back to S3 (Notice: Amazon FSx for Windows File Server does not allow you to present S3 objects as files and does not allow you to write changed data back to s3)
[Scenario]: suited for processing the 'hot data' in a parallel and distributed fashion and store the 'cold data' on Amazon S3

-AWS Glue: fully managed extract, transform, and load (ETL) service that allows customers to prepare and load data for analytics. is meant to be used for batch ETL data processing 

-[Scenario]: needs a cost-effective and resource-efficient fleet of EC2 instance that must deliver high random I/O performance.
solution-->Use instance store based EC2 instances (notice: Ec2 instances with access to S3 based storage as the solution will slow down the random I/O)
instance store is ideal for temporary storage of info that changes frequently, such as buffers, caches, scratch data etc.

-[Scenario]: a company maintains the seismological data for the past century. the data has a velocity of 1GB per min. you would like to store the data with only the most relevant attributes to build a predictive model for future analysis 
solution-->ingest the data in Kinesis Data Firehose (https://aws.amazon.com/cn/kinesis/data-firehose/) amd use an intermediary Lambda function to filter and transform the incoming stream before the output is dumped on s3 
-Amazon Kinesis Data Firehose: an ETL service that loads real-time streams into data lakes, warehouses, and analytics services
(Notice: Kinesis Data Analytics cannot directly ingest data from the source as it ingests data from Kinesis Data Streams/Kinesis Data Firehose 

-[Scenario]: the application is deployed on several ec2 instances running behind an ALB. the copany has been asked to block access from 2 countries and allow access only from the home country of the company 
solutiuon-->configure AWS WAF on the Application Load Balancer in a VPC (as WAF can be used to block or allow requests based on conditions that you specify, such as IP addresses. it allows you to restrict application access based on the geographic loca of your viewers. you can also use AWS WAF preconfigured protections to block common attacks, such as SQL injection/cross-site scripting
(Notice: security groups cannot restrict access based on the user's geographic loca)

-S3 Standard-IA and S3 One Zone-IA have a min storage duration of 30 days (so instead of 24hrs, you end up paying for 30d) and high retrieval charges-->not the most cost-effective 

-CloudFront offers a multi-tier cache in the form of regional caches that improve latency, but there are certain types that bypass the regional edge cache, and go directly to the origin
the content types that skip the regional edge cache-->
proxy methods PUT/POST/PATCH/OPTIONS/DELETE go directly to the origin: go directly from the points of presence (POPs) and don't proxy through regional edge caches 
&
Dynamic content, as determined at request time (cache-behaviour configured to forward all headers): CloudFront is a CDN. CloudFront POPs ensure popular content can be served quickly to your viewers. Dynamic content, as determined at request time (cache-behavior configured to forward all headers), does not flow through regional edge caches, but goes directly to the origin 

-when the new AMI is copied from region A into region B, it also creates a smapshot in region B as AMIS are based on the UNDERLYING SNAPSHOTS https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html

-[Scenario]: an AWS cloud architecture that throttles requests in case of sudden trafic spikes 
solution: Amazon API Gateway, Amazon SQS and Amazon Kinesis 
Amazon API Gateway-->to  prevent your API from being overwhelmed by too many requests
amazon SQS-->decouple and scale microservices, distributed systems, and serverless applications. offers buffer capabilities to smooth out temporary volume spikes without losing messages or increasing latency 
Amazon Kinesis-->ingest, buffer, and process streaming data in real-time  

-[scenario]: support both stateful and statelesss client-server comms via the APIs developed using its platform 
solution: API Gateway creates RESTful APIs that enable stateless client-server comm and API Gateway also creates WebSocket APIs that adhere to the WebSocket protocol, whcih enables stateful, full-duplex comm between client and server 
API Gateway creates RESTful APIs that: are HTTP-based, enable serverless client-server comm, implement standard HTTP methods such as GET, POST, PUT, PATCH, and DELETE
API Gateway creates WrbSocket APIs that: adhere to the WebSocket protocol, which enables stateful, full-duplex comm between client and server. route incoming messages based on message content 

-GuardDuty analyses tens of billions of events across multiple AWS data sources, such as AWS CloudTrail events, Amazon VPC Flow Logs, and DNS logs 

-[Scenario]: set up a NLB having a target group that is configured to use an EC2 auto scaling group with multiple ec2 instances (that span across multiple AZs). the company wants to improve the applications's availability as the NLB is unable to detect HTTP errors for application. these HTTP errors need a manual restart of the ec2 instances that run the web service 
solution: replace the NLB with an ALB and configure health checks on the ALB by pointing to the URL of the application. leverage the auto scaling group to replace unhealthy instances 

-[2021 Q3 new feature]: Amazon RDS custom for oracle-new control capabilities in database environment-->'with rds custom for oracle, u can now access amd customise your database server host and OS (e.g. by applying special patches and changing the databse software settings to support third-party applications that require priviledged access)

-aws lambda currently supports 1,000 concurrent executions per aws account/region. u need to contact aws support to raise the acc limit 

-Amazon FSx for Windows File Server provides fully managd, highly reliable file storage that's accessible over the industry-standard Service Message Block (SMB) protocol. it's built on Windows Server...

-for Amazon Aurora, each read replica is asscociated w a priority tier (0-15). in the event of a failure, it will promote the read replica that has the highest priority(the lowest nimber tier). if 2 or more share the same priority-->amazon rds promotes the replica that is largest in Size

-The EBS volume types fall into 2 categories: 'SSD-backed volumes' optimised for transactional workloads involving frequent read/write operations with small I/O size, where the dominant performance attribute is IOPS. 'HDD-backed volumes' optimsed for large streaming workloads where throuhput (measured in MiB/s) is a bteer performance measure than IOPS

SSD (固態應盤 卷, 固態硬碟 磁碟區)
HDD (應盤驅動器 卷, 硬碟 磁碟區)

Throughput Optimised HDD (st1) and Cold HDD (sc1) volume types cannot be used as a boot volume. General Purpose SSD (gp2), Provisioned IOPS SSD (io1), and Instance Store can be used as a boot volume 








## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1633796716762734594)
