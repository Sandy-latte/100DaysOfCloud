## Event-driven architectures on AWS 

## Cloud Research

Event-driven architectures on AWS (Amazon EventBridge, Amazon SNS, Amazon DynamoDB Streams)

-an event-driven architectures uses events to invoke and communicate between decoupled service. it's a common architectures in modern applications that are built with microservices 
event-->a change in state, or an update, such as placing an item in a shopping cart on an ecommerce website. events can carry either the state (the item purchased, its price, and a delivery address) or events can be identifiers (a notification that an order was shipped) 

-have 3 key components: event producers, event routers, and event consumers 
producer-->publishes an event to the router, which filters and pushes the events to consumers. producer services and consumer services are decoupled, which means they can be scaled, updated, and deployed independently 

Amazon EventBridge vs Amazon SNS 

-both can be used to develop event-driven applications. your choice depends on your specific needs

use EventBridge when:
-you want to build an app that reacts to events from SaaS apps or aws services (eventbridge is the only event-based service that integrates directly with third-party SaaS AWS Partners)

-it also autimatically ingests events from over 90 aws services without requiring developers to create any resources in their account.
also, eventbridge uses a defined, JSON-based structure for events, and you can also select events to forward to a target by creating rules that are applied across the entire event body

-it currently supports over 15 aws services as targets, including aws lambda, amazon sqs, amazon sns, amazon kinesis data streams, and amazon kinesis data firehose, and more

-at launch, eventbridge has limited throughputm which can be increased on request. it also has a typical latency of about 0.5 second 


use Amazon SNS when: 

-you want to build an app that reacts to high throughput/low-latency msgs that are published by other applications/microservices-->amazon SNS provides nearly unlimited throughput 

-can also be used for apps that need very High fan-out (thousands/millions of endpoints)

-msgs are unstructured and can be in any format. amazon sns supports forwarding msgs to 6 different types of targets, including aws lambda, amazon sqs, http/s endpoints, short message service (sms), mobile push, and email. the typical latency of amzon sns typical is <30 milliseconds 
-more than 30 aws services, including amazon ec2, s3, and rds-send sns msgs by configuring thr service to send them 

Amazon EventBridge 

-a serverless event bus service that you can use to connect to your applications with data from various sources. it delivers a stream of real-time data from your applications, SaaS applications, and aws services to targets (e.g. aws lambda functions, HTTP invocation endpoints using API destinations, or event buses in other aws accounts)

-eventbrideg receives an event, which is an indicator of a change in environment. it then applies a rule to route the event to a target. rules match eventss to targets nased on either the structure of the event ('event pattern'), or on a schedule
for ex., when an ec2 changes from pending to running-->you can have a rule that sends the event to a Lambda function 

-all events come to eventbridge are associated with an event bus. rules are tied to a single event bus, so they can only be applied to events on that event bus 
your acc has a default event bus, which receives events from aws servicees. you can also create custom event buses to send/receive events from a different acc/Region 

-https://docs.aws.amazon.com/zh_cn/eventbridge/latest/userguide/eb-event-bus.html
https://aws.amazon.com/cn/eventbridge/faqs/?nc1=h_ls
https://docs.aws.amazon.com/zh_cn/eventbridge/latest/userguide/eb-service-event.html
https://docs.aws.amazon.com/zh_cn/eventbridge/latest/userguide/eb-rules.html
https://aws.amazon.com/cn/event-driven-architecture/https://pages.awscloud.com/AWS-Learning-Path-How-to-Use-Amazon-EventBridge-to-Build-Decoupled-Event-Driven-Architectures_2020_LP_0001-SRV.html?&trk=ps_a134p000003yBd8AAE&trkCampaign=FY20_2Q_eventbridge_learning_path&sc_channel=ps&sc_campaign=FY20_2Q_EDAPage_eventbridge_learning_path&sc_outcome=PaaS_Digital_Marketing&sc_publisher=Google


Amazon SNS

-managed service that provides msgs delivery from publishers to subscribers (which are also known as producers and consumers)
publisher-->communicate asynchronously with subscribers by sending msgs to a topic  which is a logical access point and comm channel 
clients-->can subscribe to the sns topic and receive published mshs by using a supported endpoint type, like amazon kinesis data firehose, amazon sqs, lambda, http, email, mobile push notifications, and mobile text msgs through short message service (sms) 

-https://aws.amazon.com/cn/blogs/compute/introducing-payload-based-message-filtering-for-amazon-sns/
https://aws.amazon.com/cn/sns/faqs/
https://docs.aws.amazon.com/zh_cn/sns/latest/dg/sns-getting-started.html#step-create-queue


Amazon DynamoDB Streams 

-captures a time-ordered sequence of item-level modifications in any DynamoDB table, and stores this info in a log for uo to 24hrs. applications can access this log and view the data items as they appeared, before and after they were modified, in near-real time 
encryption at rest encrpyts the data in DynamoDB streams 

-DynamoDB Streams helps ensure the following:
a)each stream record appears exactly one time in the stream 
b)for each item that is modified in a DynamoDB table, the stream records appear in the same sequence as the actual modifications to the item 

-DynamoDB Streams writes stream records in near-real time so that you can build applications that consume these streams and take action based on the contents 

-you can enable a stream on a new tanle when you create it by using the AWS CLI or one of the AWS SDKs. you can also enable/disable a stream on an exissting table, or change the settings of a stream 

-all data in dynamodb streams is subject to a 24-hr lifetime-->you can retrieve and analyse the last 24hrs of activity for any given table-->notice: data that is >24hrs is susceptible to trimming (removal) at any moment 

-https://docs.aws.amazon.com/zh_cn/amazondynamodb/latest/developerguide/Streams.html
https://docs.aws.amazon.com/zh_cn/amazondynamodb/latest/developerguide/Streams.Lambda.Tutorial.html


## Social Proof



[Tweet](https://twitter.com/Sandy87163104/status/1626524098942709762)
