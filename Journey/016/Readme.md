AWS Storage (s3 file gateway, ebs, efs, s3)
## Cloud Research

-use aws storage gateway and s3 if the Network File System (NFS) protocol is asked to remian in place for all on-prem applications 

AWS Storage Gateway 

-use it for storing data in the AWS cloud for cost-effective and data security reasons. supports file-based, volume-based, and tape-based storage solutions 

-it connects on-prem software with cloud-based storage-->provides near-seamless integration with data security features between your on-prem IT environment and the AWS storage infrastructure 

#Amazon S3 File Gateway (the gateway provides access to objects in s3 as files/file-share mount points) 

-supports a file interface into s3 and it combines a service and a virtual software appliance-->the combination allows you to store and retrieve objects in s3 by using industry-standard file protocols, such as Network File System (NFS) ans Server message Block (SMB)
the software gateway is deployed into your on-prem environment as a VM that runs on VMware ESXi, Microsoft Hyper-V, or Linux Kernel-based VM (KVM) hypervisor 

-it is designed to simplify file storage in s3
with it, you can: store and retrieve files directly by using NFS/SMB & access data in s3 directly & manage s3 data by using lifecycle policies, CRR, and versioning
-->s3 file gateway can be seen as a file sys mounted on s3 

#EBS (https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)

-[CRUCIAL] note different EBS volume types and sizes, and how IOPS are related to volume size and type 

-can be attached to your amazon ec2 instances
after attaching a volume to an instance, you can increase size, revise the provisioned IOPS capacity, and change volume type 

-types: Solid-state drive (SSD), Hard disk drive (HDD), and Previous Generation 

a)SSD-->optimised for transactional workloads involving frequent read/write operations with small I/O size, where the dominant performance attribute is IOPS. it includes General Purpose SSD volumes and Provisioned IOPS SSD volumes 

b)Hard Disk Drive (HDD)-->optimised ofr large, streaming workloads where the dominant performance attribute is throughput. it includes Throughput Optimised HDD and Cold HDD volumes 

c)previous generation-->aws recommend using a current generation volumn type. hard disk drives that you use for workloads with small datasets, where data is accessed infrequently and performance does not come first 

@@number of available IOPs grows with the size of the volume. hence, if you need more IOPs-->must scale the volume vertically 

#Amazon EFS

-it minimises the need to provision and manage capacity. it has a web service interface that you can use to create and config file sys quickly. the service manages all the file infrastructure for you (helps reduces complexity of deploying, patching, and maintaining complex file sys configs 

-it supports NFS version 4 (NFSv4.1 and NFSv4.0). multiple compute instanes can acccess an efs sys meanwhile-->efs can thus offer a data source for workloads and applications that run on more than one compute instance/server 


## Social Proof


[Tweet](https://twitter.com/Sandy87163104/status/1627348870370828291)
