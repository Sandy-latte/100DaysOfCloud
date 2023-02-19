Running containers on AWS and NAT Gateways 

## Cloud Research

-[crucial] https://aws.amazon.com/cn/containers/faqs/?nc1=h_ls

-Container orchestration tool (https://aws.amazon.com/containers/): Amazom ECS or Amazon Elastic Kubernetes Services (Amazon EKS)

-Amazon ECS launch types: EC2 (deploy and manage your won ec2 instances cluster & when client want to use a custom thing), AWS Fargate (run containers directly, without any ec2 instances) 
https://docs.aws.amazon.com/AmazonECS/latest/developerguide/launch_types.html

#EC2 launch type-->ECS agent is installed on each ec2 instance in the cluster. ecs agent enables the orchestration tool that ecs uses to manage nodes 

Connect to the interney/other networks using NAT devices (https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat.html)

-use NAT Gateways or NAT instances to to allow reources in private subnets to connect to thr internet/other VPCs/on-premises networks 

-use NAT Gateway (managed by AWS) or NAT instance (create your own NAT device on an EC2 instance). aws recommends using NAT gateways as they offer better bandwidth and availability 

-https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-comparison.html

#NAT instances 

-the NAT device replaces the source IPv4 address of the instances with the address of the NAT device 
when the NAT device sends response traffic to the instances, the device translates the addresses back to the original source IPv4 address 

#NAT Gateways 

-use a NAT gateway soe that instances in a private subnet can connect to devices that are outside your VPC, but external services can't connect to those instances 

-when you create a NAT gateway, specify public (default) or private

-NAT gateway replaces the source IP address of the instances with the IP address of the NAT gateway

## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1627272171474104321)
