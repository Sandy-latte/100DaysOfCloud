## Optimising Architecture 

## Cloud Research

Amazon DynamoDB Accelerator (DAX) (https://aws.amazon.com/dynamodb/dax/)

-if you wanted to improve Amazon DynamoDB performance to microsecond latency-->consider Amazon DynamoDB Accelerator (DAX)

-it's a fully managed, highly available, in-memory cache for DynamoDB that's designed to deliver up to a 100-times performance improvement-from milliseconds to microseconds 

-with DAX, developers do not need to manage cache invalidation, data population, or cluster management

-why use DAX? you don't need to modify the application logic as DAX is compatible with existing DynamoDB API calls 

-DAX's designed to run within an Amazon VPC (which defines a virtual network that closely resembles a traditional data centre)


Optimising AWS Lambda-->AWS Lambda Power Tuning (which you can fine-tune the memory/power configuration for your aws lambda functions to potentially grow performance and lower costs), AWS Lambda Powertools,and AWS Lambda execution environment reuse 

-an open-source tool that helps you visualise and fine-tune the memory/power configuration of Lambda functions 
it runs in your aws acc, and supports optimisations on: cost, speed, and balanced 
https://github.com/alexcasalboni/aws-lambda-power-tuning

-it's a state machine and helps you cost-optimise your Lambda functions 

-to work with AWS Lambda Power Tuning-->first provide a Lambda function Amazon Resource Name (ARN) as input-->the state machine then invokes that function with multiple power configurations-->then it analyses all the execution logs and suggests the best power configuration
note: the input function will run in your aws acc-->it will perform HTTP requests, SDK calls, cold starts..the state machine also supports cross-Region invocations, and you can enable parallel execution to generate results in a few seconds 

AWS Lambda Powertools

-enables easier tracing, structured logging, custom metrics, batching etc. for AWS Lambda functions 
https://awslabs.github.io/aws-lambda-powertools-python/2.8.0/#features

AWS Lambda execution environment reuse 

-move specific initialisation tasks in your code so they're outside the handler

-https://docs.aws.amazon.com/zh_cn/lambda/latest/dg/best-practices.html
https://aws.amazon.com/blogs/compute/building-well-architected-serverless-applications-optimizing-application-costs/



## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1626622595868000259)
