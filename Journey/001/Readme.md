
# The First Day 

## Introduction

I intend to use the challenge to document my cloud journey. At the end of the 100DaysOfChallenge, I look forward to building relevant cloud projects and clearing the following 3 exams: AWS Certified Cloud Practitioner, AWS Solutions Architect, and AWS Sysops Administrator exams. 

## Cloud Research
(In the final process of reviewing unfamiliar AWS CCP topics when I started the challenge. See below the notes I've taken after completing mock exam 6.)
-2 services that automatically replicate data across AZs? that is, your data is available when required and protected against AZ failures. --> S3 and Amazon Aurora
RDS database engines they don't replicate automatically. you need to manually enable the multi-AZ feature. 

-recommended storage option when hosting an often-changing database on an EC2 instance? Amazon EBS (it offers block-level storage volumes that you can attach to a running EC2 instance)
Amazon EBS is the recommended storage option when you run a database on an EC2 instance

-benefits of the AWS Organisations? control access to AWS services, consolidate billing across multiple aws accounts 
it is aws billing and cost management that allows you to manage your org's payment methods

-ElastiCache? improve web application performance, provide an in-memory data storage service
elasticache improves web applications performance by allowing you to retrieve data from a fast, managed, in-memory data store

-aws lambda runs your code automatically without you adjusting capacity or manage servers. it scales your application by running code in response to each trigger

-an aws repository management system that allows for storing, versioning, and managing your application code? AWS CodeCommit 
aws CodeCommit enables companies to host secure and highly availble Git repositories 

-makes it easier for you to categorize, manage and filter your resources? aws tagging 
aws allows cutomers to assign metadata to their aws resources in the form of tags. each tag is a simple lable composed of a customer-defined key and value.
aws service catalog is used to create and manage catalogs of IT services that are approved for use on aws. it helps you meet your compliance nad governance needs

-EASIEST way to set up and manage a secure, well-architected, multi-account aws environment? aws control tower 

-what feature enables users to sign into their aws accounts with their existing corporate credentials? federation 
with Federation, you can use single-sign-on (SSO) to access yout aws accounts using credentials from your corportate directory

-access keys are long-termcredentials for an aws IAM user/aws account root user. access keys are NOT used for signing in to account. can use access keys to sign programmatic requests to the aws CLI or AWS API (directly or using the aws SDK)

-what can aws customers do to benefit from the elasticity of the aws cloud? -->take advantage of platform's 'elasticity' --> aws auto scaling, serverless computing whenever possible
Elastic Load Balancing does NOT scale RESOURCES. ELB automatically distributes incoming application traffic across multiple targets (ec2 instances, containers, IP addresses, and Lambda functions)


## Social Proof

[Tweet ](https://twitter.com/Sandy87163104/status/1620496618389897218)
