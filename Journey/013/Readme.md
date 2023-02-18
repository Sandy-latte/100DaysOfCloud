Optimising Architectures (case 2)-Amazon CloudFormation and IaC & Error retries and exponential backoff in aws & Athena Data Optimisations 

## Cloud Research

Amazon CloudFront (https://aws.amazon.com/cloudfront/)

-a web service that speeds up the distribution of your static and dynamic web content (e.g. .html, .css, .js, and image files) to your users
it delivers content via 'edge locations'-->a worldwide network of data centres

-allows custome SSL certs (issued by ACM), custom domain names, and further distributed denial of service (DDoS) protection which is powered by AWS WAF and AWS Shield

Amazon Cognito (https://aws.amazon.com/cognito/)

-cognito (rather than Amazon API Gateway) to send data to Amazon Kinesis
the solution would require refactoring code in the JavaScript library that sends the clickstream data. yet it would also bypass API Gateway-->thus reduce costs 

-with this, you can have a mobile JavaScript library that assumes a role with a web identity (and thaat role must have a strict policy attached-for ex., the policy could only grant the API operation on a specific kinesis)
(optional: https://docs.aws.amazon.com/zh_cn/STS/latest/APIReference/API_AssumeRoleWithWebIdentity.html)

Amazon CloudFormation and IaC 

-transforming the entire environment into a template that could be further replicated for each of the client's client-->treating IaC with AWS CloudFormation 

-CloudFormation helps model and set up your aws resources->you can focus more on your applications that run in the aws 
you create a template that describes all your desired aws resources (for ex., EC2 instances/RDS instances)-and CloudFormation provisions and configures the resources for you-->no need t individually create and configure aws resources 

-see https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/CHAP_TemplateQuickRef.html for examples of how to use CloudFormation templates 

-[CRUCIAL] learn how to create infrastructure template as you can replicate customer workloads across multiple aws accs/Regions 

Error retries and exponential backoff in aws (https://docs.aws.amazon.com/general/latest/gr/api-retries.html)

-implementing retries in the client application increases the application reliability & reduces costs for developer (if using AWS SDKs, they already practice exponential backoffs by default)
-->benefit: the exponential behavior backoff default behavior of using Amazon Cognito on the client side to send data to Kinesis (rather than using a custom routine that sends data to API Gateway

-should implement a max delay interval and number of retries (the number values should be set based on the performing operation and network latency)

Tips for Amazon Athena Data Optimisations (https://aws.amazon.com/blogs/big-data/top-10-performance-tuning-tips-for-amazon-athena/)
Storage (1-5) & Query Tuning (6-10)

-1)partition your data-->divide table into parts and keep the related. partition can be virtual columns (you define them at table creation, and they help reduce the amount of data scanned per query) (see more on https://aws.amazon.com/blogs/big-data/improve-amazon-athena-query-performance-using-aws-glue-data-catalog-partition-indexes/)

-bonus tips:
optimising Partition Processing using partition projection (https://docs.aws.amazon.com/athena/latest/ug/partition-projection.html)-->ideal to use it when your partition's schemas are the same or if the tables' schema always accurately describes the partitions schemas. it can be used to partition very high cardinality columns (e.g. IDs/date ranges at very fine granularity)
[crucial]https://docs.aws.amazon.com/zh_cn/athena/latest/ug/partition-projection.html

-2)bucket your data-->specify one or more columns with rows that you want to group together, and put those rows into multiple buckets-->allows you to query only the bucket that you need to read-->in turn reduces the cost of running the query 
a good column use for bucketing would be a primary key (e.g. a user ID for systems)

-3)use compression-->as it significantly speeds up your data (as smaller data size reduces the data scanned from s3-->reduce costs and network traffic from s3 to athena 

-4)optimise file sizes-->ensure file formats are splittable helps with parallelsim. too small files are not ideal as the engine might spend extra time with the overhead of actions-->solution: use the S3DistCP on EMR (|use it to combine smaller files into bigger objects)

-5)optimise COLUMNAR data store generation. common data stores: Apache Parquet and Apache ORC
parameters that you can tune: block size (stripe size), compression algorithm on data blocks 

Query tuning-->optimise ORDER BY & joins & GROUP BY, use approx functions, include only the columns that you need

-6)Optimise ORDER BY-->if using the ORDER BY clause to look up the bottom/top N values-->use a LIMIT clause to reduce sort cost

-7)Optimise joins-->when joining 2 tables, specify the larger table on the left side and smaller on the right-->less memory is used and query runs faster 
when joining 3 tables-->join the large table with the smallest table first to reduce the intermediate results 

-8)optimise GROUP BY-->when using GROUP BY, order the columns by the highest cardinality(the most unique values, distributed evenly) to the lowest 

-9)use approx functions-->use 'approx_distinct()' when an exact number may not be required (e.g. if you're looking for which web pages to dive into) (as it minimise the memory usage by counting unique hashes of values rather than entire strings with the drawback of a standard error of 2.3%

Bonus tip-->speed up queries producing large result sets using UNLOAD-->with UNLOAD, you can split the results into multiple files in s3, which reduces the time spent in the writing phase 

## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1627047372575350784)
