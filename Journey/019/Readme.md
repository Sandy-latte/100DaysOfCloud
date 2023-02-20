Infrastructure Logging Services 

## Cloud Research

-include: AWS CloudTrail, AWS Config, VPC Flow Logs, and Amazon GuardDuty

#AWS CloudTrail-->typically delivers logs within an average of 15min after an API call. with CloudTrail, user in an organisations management acc can create an org trail that logs all events for all aws accs in the org

#AWS Config
[crucial] understand the differences between AWS CloudTrail and AWS Config 

-it offers a detailed view of how AWS resources are configured in your aws acc. (the config includes how resources are related to one another and you'll be able to see the configs and relations changes). use AWS Config to get an inventory of the resources that you have in your aws acc, then you apply rules for how those resources are configured 
(AWS resource-->an entity that you can work with AWS, suhc as EC2 instance, an EBS volume, a security group, a VPC)

-resource config, auditing and compliance, managing and troubleshooting config changes, security analysis 

#VPC Flow Logs 

-a feature that you can use to capture info about the IP traffic that goes to and from network interfaces in your VPC

-flow log data can be published to Amazon CloudWatch Logs/Amazon S3 

-flow logs help with: diagnosing overly restrictive security rules, monitoring the traffice that reaches your instance, determining the direction of the traffic to and from the network interfaces 

-flow log data is collected outside the path of your network traffic and thus it does not affect network throughput/latency 

#Amazon GuardDuty https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html

-security monitoring service that analyses and processes data sources, such as CloudTrail data events for Amazon S3 logs, Cloudtrail management event logs, Amazon EBS volume data, Amazon EKS audit logs, and Amazon VPC flow logs 

-uses threat intelligence feeds and ML to identify unexpected, malicious, unauthorised activity within your aws environment

## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1627684641845960704)
