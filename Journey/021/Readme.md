Multi-acc best practices 
## Cloud Research

Multi-acc environments 

-core concepts of AWS Organisations and service control policies (SCPs). also it offers suggestions on different organisation unit (OU) structures for different use cases (such as a corporate OU, a production public-facing OU, a production internal-facing OU, and a security OU)
https://aws.amazon.com/cn/blogs/industries/best-practices-for-aws-organizations-service-control-policies-in-a-multi-account-environment/

-Organsing your aws environment using multiple accs-->https://docs.aws.amazon.com/zh_cn/whitepapers/latest/organizing-your-aws-environment/benefits-of-using-multiple-aws-accounts.html

-Estaablishing your best practice with AWS environemnt-->https://aws.amazon.com/cn/organizations/getting-started/best-practices/


Tag policies and SCPs 

-you can set tag policies with Organisations 

-tag policy might be adequate if you as IaC to provision environemnts. with IaC, environments will be created from a CloudFormaton template, and you'll be able to embed tags in the template 

-use SCPs if you wanna prevent creation of new aws resources that aren't taggged-->that is, use SCPs to ensure the aws resources are created only if a certain tag exists


## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1628064949300875264)
