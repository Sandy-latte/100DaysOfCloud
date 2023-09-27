exercise 2: building a Proof of Concept for data analytics solutions

## Task

-create IAM roles and policies

-create the object storage s3 bucket to store clickstream data

-create the Lambda function for kinesis data firehose to transform data 

-create a kinesis data firehose delivery stream to deliver real-time streaming data to s3

-create a REST API to insert data 

-create an athena table to view the obtained data 

-create QuickSight dashboards to viz data 

## Introduction

the customer's a restaurant owner who wants to derive insights for all menu items that are ordered in their restaurant. as the restaurant have limited staff for running and manintaining the solution, u will build a proof of concept by using the services 

## Task 1-creating the IAM roles and policies

## Task 2-creating an s3 bucket 

## Task 3-creating a lambda function

## Task 4-creating a kinesis data firehose delivery stream 

4.1-creating a kinesis data firehose delivert stream
4.2-copy the ARN of the IAM role

## Task 5-adding the fireehose delivery stream ARN to the S£ bucket 

## Task 6-creating an API in APIGateway

## Task 7-creating an athena table

you create an athena table. u also usesql query to view the payloads u create that u inserted with REST API
'begin querying ur data' card, choose 'explore the query editor'-->settings tab, choose 'manage'-->choose'browse'-->'editor' tab, 'tables and iews' section, on the 'create' menu, choose 'create table as select'-->'query', replace the code -->replace 'location', 'storage.location.template'-->run-->create a new query-->select* from your data-->run
the query should produce results w the entries that u ran in API Gateway

## Task 8-vizualise ur data w quicksight 

for new users
sign up for quicksight-->standard-->fill in the basic info-->finish-->after signing up, go to quicksight console-->manage quicksight-->in the navigaton pane, choose 'security and permissions' and in 'quicksight access to aws service', choose manage -->under s3, choose 'select s3 buckets'-->select 'write permission for athena workgroup'-->finish-->return to quicksight console-->in the 'analyses' tab, choose 'new analyses'-->choose 'new dataset'-->choose athena and config: 'name resources', 'select workgroup'-->choose 'create data source'-->'create ur table', choose ur data table, and choose select-->in the 'finish dataset creation' dialog box, make sure that 'import to SPICE for quicker analytics' is selected, and choose 'visualisation'

## Task 9-deleting all resources




