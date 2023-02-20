Optimising architectures (case 3)

## Cloud Research

Disaster recovery approaches (cost low to high; Recovery Time Objective/RPO long to short): backup & restore, pilot light, warm standby, multi-site active/active (zero downtime)

#Backup and restore 

-can be used to mitigate against a regional disaster by replicating data to other AWS Regions. besides data, you must redeploy the infrastructure, config, and application code in the recovery Region. to enable infrastructure to be redeployed fast without errors-->use IaC, with services like AWS CloudFormation/AWS Cloud Development Kit (AWS CDK)
IaC is crucial as it might be complex to restore workloads in the receovery Region and lead to increased recovery time without IaC-->besides backing up your user data, backup your code and configs also-including AMIs that you use to create EC2 instances 

-use AWS CodePipeline to automate the redeployment of your application code and configs 

#Multi-site active active

-hot standby uses an active/passive config, where users are directed to a single region and disaster recovery Regions don't take traffic 
use multi-site active/active if you're gonna stand up a full environment in the 2nd Region 

AWS Direct Connect wirh AWS VPN for failover https://aws.amazon.com/cn/premiumsupport/knowledge-center/dx-configure-dx-and-vpn-failover-tgw/?nc1=h_ls

-to make the connection to AWS more resilient-->consider using amazon site-to-site VPN as a failover for aws direct connect and thus the connection is redundant (as the setup would work as a backup if the aws direct connect connection became unavailable


Automatic scaling for containers-->when using amazon ECS, think about scaling both the underlying EC2 cluster and the containers 

#scaling the cluster 

-when using an auto scaling group with managed scaling , ECS creates 2 custom Amazon Cloudwatch metrics, and a target tracking scaling policy that attaches to your Auto Scaling group-->amazon ECS then manages the scale-in and scale-out actions of the Auto Scaling group based on the load that your tasks put on the cluster 


#scaling the containers 

-amazon ECS Service Auto Scaling supports the below scaling policies(increase/decrease the number of tasks that your service runs based on different metrics):

a)Target tracking scaling policies (recommended): based on a target value for a specific metric. similar to thermostat, you select the temperature, and it manages the temperature 

b)step scaling policies: based on a set of scaling adjustments (step adjustments). the adjustments vary based on the size of the alarm breach 

-https://docs.aws.amazon.com/zh_cn/AmazonECS/latest/developerguide/cluster-auto-scaling.html
https://ecsworkshop.com/capacity_providers/ec2/
https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html

Auto Scaling for Amazon RDS-->https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIOPS.StorageTypes.html#USER_PIOPS.Autoscaling

## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1627658650054545415)
