
# Exam Notes Review 
## Cloud Research


-the term 'serverless' is not only limited to compute services-->a serverless service is a service that does not need the customer to manage the infrastructure layer/operating system/platform layer. 

exam 1

-Access keys consist of an access key and secret access key, which are used to sign programmatic requests to aws usisg the CLI/SDK

-CloudWatch monitors aws cloud resources and the applications you run on aws.-->use cloudwatch to collect and track metrics, collect and monitor log files, set alarms, and automatically react to changes in your aws resources

-cloudtrail can be used to monitor all user interactions with the aws environment 

-IAM user groups help org organise employees into teams and then assign the appropriate permissions for each team 

-aws organisations can be used to group aws accounts (not IAM users). aws org help you to centrally managebilling; control access, compliance, and security; and share resources across multiple aws accounts 

-aws health dashboard provides: 1) detailed troubleshooting guidance to address aws events impacting yoiur resources 2) personalised view of aws service health 

-which help adhere to the principle 'design for failure and nothing will fail'? AZs, Elastic Load Balancing 
multiple AZs --> ensure fault-tolerant. ELB --> regularly perform health checks and distribute traffic only to healthy instances 

-benefits of having infrastructure hosted in aws? 1) all of the physical security and most of the data/network security are taken care of for you 2) increasing speed and agility 


-best s3 storage class for data with unpredictable access patterns? Amazon s3 intelligent-tiering 
s3 intelligent-tiering is designed to optimise costs by automatically moving data to the most cost-effective access tier. without performance impact. 
s3 standard provides high durability, availability, and performance storage for frequently accessed data 
s3 standard-infrequent access (s3 standard-IA) is for data that is accessed less frequently, but requires rapid access when needed 
s3 glacier flexible retrieval (formerly s3 glacier) is a low-cost storage class for archive data that is accessed 1-2 times per year 

-when dealing with a 'single point of failure'-->build as much automation as possible in detecting and reacting to failure. whihc would help? ELB and Auto Scaling 
should build as much automation as possible in detecting and reacting to failure. -->can use ELB and Route53 to configure health checks and mask failure by routing TRAFFIC to healthy endpoints. also, auto-scaling can be configured to automatically replace unhealthy nodes. can also replace unhealthy nodes using the ec2 auto-recovery feature or services such as aws OpsWorks and aws elastic beanstalk. 

-amazon athena is an interactive query service that is mainly used to analyse data in s3 using standard sql

-ec2 is a server-based compute service. fault-tolerance is not built-in-->have to architect for fault tolerance 

exam 2

-primary storage service used by amazon rds database instances? Amazon ebs
DB instances for amazon rds for mysql, mariadb, postgresql, oracle, and microsoft sql server use amazon EBS volumes for databsed and log storage 

-which allow you to run CONTAINERIZED applications on a cluster of ec2 instances? amazon elastic kubernetes service, amazon ecs 
amazon elastic container service (amazon ecs) -->highly scalable, high-performance container orchestration service that supports Docker containers and allows you to easily run and scale containerised applications on aws. ecs eliminates the need for you to install and operate your own container orchestration software, manage and scale a cluster of virtual machines, or schedule containers on those virtual machines
amazon elastic kubernetes service (amazon eks)-->a managed service that allows you to use kubernetes to run and scale containerised application in the cloud or on-premises. kubernetes is an open-source container orchestration system that allows you to deploy and manage containerised application at scale

-Amazon VPC allows you to provision a logically isolated section of the aws cloud where you can launch aws resources in a virtual network that you define. you have complete control over your virtual networking environment
Internet gateway's a VPC component that allows comms between your vpc and the internet 

-physical hardware should be considered when performing a TCO (the total cost of ownership) analysis to compare the costs of running an application on aws rather than on-premises
when comparing aws with on-premises tco, customersshould consider consider all costs of owning and operating a data centre. things to consider include: costs of facilities, physical servers, storage devices, networking equipment, cooling and power consumption, and labor IT
The Total Cost of Ownership (TCO) is often the financial metric used to estimate and compare direct and indirect costs of a product or a service. Cooling and power consumption, data center space, data center real estate and Labor IT cost are examples of the indirect costs of a physical data center and should be included in TCO analysis
the TCO gap between aws infrastructure and traditional infrastructure has widened over the recent years-->aws continues to lower the cost of cloud computing for its customers 

-the amazon rds features that can be used to improve the availability of your database? read replicas(provide enhanced performance and durability for database instances), multi-az deployment 

-purpose of PATCHING-->to resolve funtionality issues, improve security or add new features 

-edge locas are used in conjunction with the CloudFront service to cache common responses and deliver content to end-users with low-latency. with cloudfront, your users can benefit from accelerated content uploads. as the data arrives at an edge loca, data is routed to aws storage services over an optimised network path 

-which are designed with native multi-az fault tolerance in mind? amazon dynamodb, s3
ebs-->ebs volume data is replicated across multiple servers within the same AZ
efs-->is stored redundantly across multiple azs providing better durability compared to ebs volumes 

-amazon simple queue service(integration service)-->can be used to store and reliably deliver messages across distributed systems 

exam3

-the aws well-architected framework is based on 6 pillars: operational excellence, security, reliability, performance efficiency, cost optimisation, sustainability
which activity upports the operational excellence pillar of the WAF? using aws cloudformation to manage infrastructure as code 

-benefits of using an aws-managed service? lowers operational complexity, allows custoemr to deliver solutions faster 

-scale automatically without your intervention-->s3, lambda 

-data sovereignty-->the concept that info which has been converted amd stored in binary digital form is subject to the laws of the country in which is located. --> a factor to consider when choosing region

-benefits of implementing a tagging strategy for aws aws resources? quickly identify resources that belong to a specific project, track aws spending across multiple resources 

-aws transit gateway-->to simplify the connection management among the vpcs. with aws transit gateway, each vpc only has to connect to the transit gateway and not to every other vpc
aws private link--> enables you to securely connect your vpcs to supported aws services: to your own services on aws, to services hosted by other aws accounts, and to third-party services on aws marketplace 

-which can be used to deploy the required SSL server certs? AWS ACM, AWS IAM
to enable HTTPS connections to your website /application in aws-->need an SSL/TLS server cert-->use a server cert provided by ACM/one that you obtained from an external provider-->use ACM or IAM to store and deploy server certs 
use IAM as a certificate manager only when you must support HTTPS connections in a region that is not supported by ACM. IAM supports deploying certs in all regions, but you musy obtain your cert from an external provider for use with aws 


exam 4

-running ec2 instances in parallel-->best suited for processing a large number of binary files
Horizontal scaling-->adding several smaller instances when workloads go up, rather than adding extra CPU, memory, or disk capacity to a single instance 

-Amazon Cloud Directory-->allows the organisation of hierarchies of data across multiple dimensions. it makes it easy for you to organise and manage all your application resources (e.g. users/groups/locas/devices/policies)

-AZs within a region are connected over low-latency links-->make synchronous replication of your data possible 

-aws pricing calculator-->helps you estimate your monthly cost more efficiently 
aws cost explorer-->used to explore and analyse your historical data spend and usage. also, it can be used to estimate aws services cost based on your previous consumption-->limited to EXISTING PROJECTS only 

-amazon s3 --> a serverless service. aws customers can store as much data as they want and access it when they need it, without having to think about capacity, hard disk configurations, replication, and other admin burden
amazon elastic container service (amazon ecs)--> a container orchestration service that is used to run containerised applications on aws 

-consider below when you estimate the cost of using amazon ec2:
clock hours of server time, instance type, pricing model, number of instances, load balancing, elastic IP addresses, OS and software packages 

-AWS SDKs and AWS CLI-->used by customers to interact with aws IAM

-you can use the aws IAM console, the aws CLI, or the aws API to enable a virtual MFA device for an IAM user in your account 

-auto scaling groups scales ec2 instances in multiple AZs to increase application availability and fault tolerance 


exam 5 

-easiest way to launch a simple WordPress (dynamic) website on aws-->run WordPress on an Amazon Lightsail instance 
a dynamic website relies on server-side processing, and it uses server-side scripts such as PHP, JSP, or ASP.NET

-AWS Direct Connect--> for businesses to establish a dedicated network connection from their on-premises datacentres to aws. with aws direct connect, customers can build private connectivity between aws andd theor data centre/office

-(x)"You should deploy critical components of your application in the Availability Zone that you trust" -->all AZs have the same level of security 

-EC2 (rather than amazon rds) allows you to install and run custom relational database software 
rds provides 6 database engines to choose from. these engines are already installed and ready to be used. the customer does not install the actual database software on rds, nor has the access to the underlying host as it's managed 

-amazon redshift and amazon emr-->provide server-based and serverless compute options 

-help secure your sensitive data as it travels to and from s3--> use SSL(secure socket layer)/TLS (transport layer security) and encrypt the data prior to uploading it
data protection refers to protecting data while in-transit (as it travels to and from s3) and at rest (while it's stored on disks in aws data centres)
data in-transit:
you can protect data in transit by using: SSL/TLS and client-side encryption
data at rest:
server-side encryption and client-side encryption 

-delete root user access keys if you do not need them. 
(IMPORTANT)
there're some specific tasks that are restricted to the aws account root user. for ex., only the root user can perform the below:
1. change your account settings (include the account name, root user password, and email address)
2. view certain tax invoices
3. close your aws account
4. change/cancel your aws support plan 
5. activate IAM access to thr Billing and Management console 
6. configure an amazon s3 bucket to enable MFA Delete

-s3 pricing is based on the 4: 
1. total amount of data (in GB) stored on s3
2. storage class
3. amount of data transferred of aws from s3
4. number of requests to s3


## Social Proof



[Tweet](https://twitter.com/Sandy87163104/status/1620898027400757248)
