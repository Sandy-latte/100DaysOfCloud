Automatic Account Provisioning (AWS CloudFormation, AWS Control Tower, AWS Service Catalog) 

## Cloud Research

AWS CloudFormation 

-[crucial] https://www.wellarchitectedlabs.com/reliability/100_labs/100_deploy_cloudformation/

AWS Control Tower https://docs.aws.amazon.com/controltower/latest/userguide/what-is-control-tower.html
https://docs.aws.amazon.com/controltower/latest/userguide/terminology.html

-got features, such as landing zone, controls, account factory, dashboard 

-extends the capabilities of organisations. to help protect your organisations and accs from being affected by drift (or divergence from the best practices), AWS Control Tower applies preventive and detective controls (or guardrails) 
for ex., you can use guardrails to help nsure that security logs and necessary cross-acc access permissions are created, but not altered

-it uses CloudFormation StackSets to set up resources in your accs. each stack set has stack instances that correspond to accs, and to aws Regions per acc. AWS Control Tower deploys one stack setinstance per acc and Region 

(stack: a collection of aws resources that you can manage as a single unit

stack instance: a refernce to a stack in a target acc within a Region)

AWS Service Catalog https://docs.aws.amazon.com/servicecatalog/latest/adminguide/introduction.html

-with it, organsiations can create and manage catalogs of IT serivces that are approved for aws. organisations can use aws service catalog to centrally manage commonly deployed IT services 

-it provides the benefits: standardisation, self-service discovery and launch, fine-grained access control, extensibility and version control 

## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1627741373381152802)
