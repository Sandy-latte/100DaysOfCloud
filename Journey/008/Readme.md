## Decoupling solutions on AWS (Part 1)

## Cloud Research

Patterns for integrating microservices (https://docs.aws.amazon.com/prescriptive-guidance/latest/modernization-integrating-microservices/integrating-patterns.html)

-1)APIgateway pattern
-2)decouple messaging pattern 
-3)pub/sub pattern 

-focus on decouple messaging pattern in the following 

-a loosely coupled architecture decreases the bottlenecks that are caused by synchronous comm, latency, and I/O operations
-->Amazon SQS and AWS Lambda are often used to implemeent asynchronous comm between different services 

-use asynchronous model if:
a)you want to create loosely coupled architecture 
b)all operations don't need to be completed in a single transaction, and some operations can be asynchronous 
c)the downstream system can't handle the incoming transactions per second (TPS) rate. the msgs can be written to the queue and processed based on the availability of resources 
d)downside-->the actions of business transactions are synchronous. altho the calling sys receives a response, some part of the transaction might still continue to be processed by downstream systems 


Building storage-first serverless applications with HTTP APIs service integrations (https://aws.amazon.com/cn/blogs/compute/building-storage-first-applications-with-http-apis-service-integrations/)

-common pattern for serverless API backend
Amazon API Gateway-->AWS Lambda-->Amazon ssImple Queue Service 
(using API Gateway as a proxy to an aws lambda function is a common pattern in serverless applications. the lambda functions handles the business logic and comms with other aws/third-party services to route, modify, or store the processed data. place the data in sqs queue for processing downstream. developer takes responsiblity of handling errors and retry logic within the lambda code


-storage first pattern for serverless API backend 
Amazon API Gateway-->Amazon Simple Queue Service-->AWS Lambda 
(uses native error handling with retry logic/dead-letter queues aat the sqs layer. by directly integrating api gateway to sqs, developers can increase application reliability while reducing lines of code)

the first 5 service integrations: amazon eventbridge, amazon kinesis data streams, sqs, aws system manager's appconfig, and aws step functions 

-customers can create APIs and webhooks for their business logic hosted in the aws services
securing and monitoring the applications by taking the advantage of HTTP APIs features (e.g. authorizers, throttling, and enhanced observability)

## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1626544098575261702)
