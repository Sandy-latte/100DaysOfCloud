## Exercise 1-Architecting Solutions: Building a Proof of Concept for a Serverless Solution 

## Create the following resources: IAM policy and user, DynamoDB table, Lambda functions, SQS queue, SNS topic, API Gateway, CloudWatch Logs

## Intro

✍️ use a REST API to place a database entry in the Aamzon SQS queue. Amazon SQS will then invoke the 1st Lambda function, which inserts the entry into a DynamoDB table. After that. DynamoDB will capture a record of the new entry in a database and invoke a 2nd Lambda function. the function will pass the databse entry to Amazon SNS. After Amazon SNS processes the new record, it'll send u a notification through a specified email address 

## Task 1-Setup: Creating IAM policies and roles 

for daily operations and tasks, aws recommends using an IAM user/IAM roles to access specific services and features. IAM policies, users, amd roles are offered at no additional charge (rather than root user). in task 1, we create custom IAM policies and roles to grant limited permissions to specific aws services 

1.1: Creating custom IAM policies with the code to run under JSON tab
-a policy to put items into the DynamoDB table 
-a policy for Amazon SNS to get, list, and publish topics that are received by Lambda 
-a policy for Lambda to get records from DynamoDB Streams 
-a policy for Lambda to read messages that are placed in amazon SQS

1.2: creating IAM roles and attaching polices to the roles

## Task 2-Creating a DynamoDB table 

we create a DynamoDB table that ingests data that's passed on through API Gateway. 
create table and configure 'Table', 'Partition key', and 'Data type'

## Task 3-creating an SQS queue

we create an SQS queue. in the architecture designed for the exercise, Amazon SQS receives data records from API Gateway, stores them, and then sends them to a database 

## Task 4-creating a Lambda funcion and setting up triggers 

4.1-creating a lambda function for the Lambda-SQS-DynamoDB role: Lambda-->Create function and config: 'function option', 'function name', 'runtime', 'change default execution role', 'existing role'-->create function

4.2-setting up amazon sqs as a trigger to invoke the function: function overview-->add trigger-->for trigger config, enter sqs and choose the service in the list-->for 'sqs queue', choose 'POC-Queue'

4.3-adding and deploying the function code: on the 'POC-Lambda-1' page, in the Code tab, replace the default lambda function code with the exercise provided code-->choose 'deploy'

4.4-testing the POC-Lambda-1 Lambda function 

## Task 5-enabling DynamoDB Streams

'Tables' section of the navigation pane, choose 'Update settings'-->in the 'Tables' card, ensure that the 'orders' table is selected-->'exports and streams' tab-->in the 'DynamoDB stream details' choose 'Enable'-->for 'view type', choose 'new image'-->choose 'enable stream'

## Task 6-create an sns topic and setting up subcriptions

6.1-creating a topic in the notification service: on the 'create topic' card, enter 'POC-Topic' and next step-->in the 'details' section, keep the 'standard' topic type selected and choose 'create topic'-->on the 'POC-Topic' page, copy the ARN of the topic 

6.2-subcribing to email notifications: create subscription-->for 'top ARN', ensure that the box contains the ARN for POC-Topic-->to receive notifications, for 'Protocol', choose 'Email'-->for 'endpoint', enter ur email address-->create subscriptiomn 

## Task 7-creating an AWS Lambda function to publish a message to the SNS topic

7.1-create a POC-Lambda-2 function: creeate function and configure the following: 'function option': author from scratch, 'function name': POC-Lambda-2, 'Runtime': Python 3.9, 'Change default execution role': Use an existing role, 'Existing role': Lambda-DynamoDBStreams-SNS. the role grants permissions to get records from DynamoDB Streams and send them to Amazon SNS

7.2-setting up DynamoDB as a trigger to invoke a Lambda function. in the function overview section, 'Add Trigger' and config: 'Trigger Configuration': DynamoDB, 'DynamoDB table': orders. keep the remaining default settings and choose 'Add'. In the 'configuration' tab, ensure in the Triggers section and that the DynamoDB state is enabled 

7.3-configuring the second Lambda function 

7.4-testing the POC-Lambda-2 lambda function

## Task 8-creating an API with Aamzon APIGateway

we create a RESTFUL API. API acts as a comm bridge between ur device and the aws services
on the 'RESTAPI' card, choose 'POST'. in the 'POST-setup', pane, config: 'Integration type', 'aws region', 'aws service', 'aws subdomain', 'HTTp method': Post, 'Action type': use path override, 'Pathoverride', 'execution role', 'content handling'
choose the 'integration request' card-->expand 'HTTp header'-->add header-->fill in 'name', 'mapped form'
expand 'mapping templates' and for 'request body passthrough'-->choose never
choose 'add mapping template' and for 'content type', enter application/json
generate template

## Task 9-testing the architecture by using API Gateway 

in the APIGateway console, return to the 'POST-Method Execution' page and choose Test
in the 'Request Body' box, enter sth like this: {  "item": ".....",
"customerID":"...."} choose 'TEST'

## Task 10-cleaning up

delete everything we just created in the task

## Reflection
-as I'm still a beginner level AWS learner, it took me about an hour to complete the exercise. To familiar myyself more with the aws practical when possible 




**Add a cover photo like:**
![placeholder image](https://via.placeholder.com/1200x600)

