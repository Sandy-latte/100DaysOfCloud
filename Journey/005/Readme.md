
## Cloud Research

Compute 

✍️ AWS Lambda 
-Lambda functions can run for up to 15min-->processes that need >15min to run, use other aws compute services for hosting 

-when using lambda, you are only responsible for your code-->makes it easier to optimise for operational efficiency and low operational overhead 

-lambda manages the compute fleet, which offers a balance of memory, CPU, network, and other resources to run your code -->since lambda manages the resources-->you cant't log in to compute instances or customise the OS on the provided runtimes

-manages capacity, monitoring, and logging your lambda functions 

-if you need to manage your own compute resources-->EC2, AWS Elastic Beanstalk 

-can be used for any application virtually/backend that requires compute and that runs in <15min. Common use cases include: web backends, Internet of Things (IoT) backends, mobile backends, file or data processing, stream or message processing, and more 

-if the requirements include reducing operational overhead, optimising for cost, or optimising for performance efficiency -->lambda 

-highly performant and cost efficient 

✍️ Amazon API Gateway 

-when you need to find a way to expose the backend Lambda function-->Amazon API Gateway integrates with Lambda-->provides a way to expose the backend service without exposing to the open internet 

-a fully managed service that enables developers to create/publish/maintain/monitor/secure API at any scale

-APIs act the front door for applications. with API Gateway, you can create RESTFUL APIs and WebSocket APIs that enable real-time 2-way comm applications

-API Gateway supports containerised and serverless workloads and web applications

✍️ Amazon EC2

-provides resizable compute capacity in the cloud -->that is, it provides virtual machines in the cloud 

-consider the 'operational overhead' that EC" requires when designing solutions for customers. you have a lot of control over amazon EC2, but that control means also that you'll have overhead for managing the service 

-when choosing between lambda and ec2-->if the client was willling to rewrite code, have a spiky demand for their workload-->choose lambda since lambda minimises idling resources during low volume times

✍️ Amazon ECS

-fully managed container orchestration service that you can use to deploy, manage, and scale containerised applications

-serverless by default with AWS Fargate: Fargate is built into amazon ECS, and it reduces the time you need to spend on managing servers, handling capacity panning, or figuring out how to isolate container workloads for security 

-security and isolation by design: it natively integrates with tje tools you already trust for security, identity, and management and governance-->help you get to production quickly 

-autonomous control plane operations: a fully managed service with aws configuration and operational practices built-in-with no control plane, nodes, or add-ons for you to manage. it natively integrates with both aws and third-party tools-->makes it easy for teams to focus on building the application rather than the environment 

✍️ Amazon EKS 

-a managed service that you can use to run Kubernetes on aws without needing to install, operate, and maintain your own Kubernetes control plane or nodes 

-it offers: running and scaling the Kubernetes control plane across multiple aws azs, scaling control plane instances based on load, detecting and replacing unhealthy control plane instances, and providing automated version updates and patching for them 

-integrates with the aws services to provide scalability and security for your applications:
1. Amazon Elastic Container Registry (Amazon ECR for container images)
2. ELB for load distribution 
3. IAM for authentication 
4. VPC for isolation 
5. it runs up-to-date versions of kubernetes, so you can use all of the existing plugins and toolig from the kubernetes community 

-you can migrate any standard kubernetes application to amazon EKS with virtually no code modification 

✍️ AWS Fargate 

-can be used with amazon ECS to run containers without managing servers/clusters of EC2 instances 

-reduces your time and need to provision, configure, or scale clusters of virtual machines to run containers 

-when you run your tasks with the Fargate launch type--> you package your application in containers, specify the CPU and memory requirements, define networking and IAM policies, and launch the application

-each Fargate task has its own isolation boundary and doesn't share the underlying kernel, CPU and memory resources, or elastic network interface with another task 

-with amazon ECS on aws fargate capacity providers--> you can use both Fargate and Fargate Spot capacity with your amazon ECS tasks. with Fargate Spot, you can run interruption-tolerant amazon ECS tasks at a discounted rate, compared to the Fargate price. Fargate Spot runs taks on spare compute capacity-->when aws needs the capacity back, your tasks wil be interrupted with a 2-min warning notice


## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1621958261372080132)
