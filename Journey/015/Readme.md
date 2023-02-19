Amazon RDS

## Cloud Research

Read replicas 

-read replicas make RDS more available and offer enhanced performance and durability for amazon rds db instances 

-if you need more CPU capabilities but don't need more storage (as read replicas offload some workload to a secondary instance)

Scale up instance Vertically 

-vertically scale up instance and choose a larger instance size when you need more CPU and storage for an instance 

Enable RDS storage auto scaling (horizontally)

-if you only need more storage, but need more CPU
enable scaling storage horizontally by allocating more storage volumes for your instance manually/enabling RDS storage auto scaling 

Storage type changing for increased performance-->General Purpose SSD, Provisioned IOPS, Magnetic 

#General Purpose SSD-->cost-effective storagee. the volumes deliver single-digit millisecond latencies and ability to burst to 3,000 IOPS for extended time 
baseline performace is determined by the volume's size

#Provisioned IOPS-->designed to meet the needs of I/O-intensive workloads (espically database workloads which need low I/O latency and consistent throughput)

#Magnetic-->magnetic storage for backward compatibility (use general purpose SSD/Provisioned IOPS for new storage needs). the max amount of storage is less than the other storage types 

-https://aws.amazon.com/cn/rds/features/read-replicas/
https://aws.amazon.com/cn/rds/features/multi-az/
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.DBInstance.html

AWS DMS

-you create a migreation task with connection to the source and target databases, AWS DMS takes care of the rest 

## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1627326553196568576)
