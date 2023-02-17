## Decoupling Solutions on AWS (Part 2) 

## Cloud Research

Amazon SQS (https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/working-with-messages.html#setting-up-long-polling)

-a fully managed, msg queueing service that can be used to decouple and scale microservices, distributed sys, and serverless apps

-it helps developers focus on differntiating work (as it reduces the complexity and overhead associated with managing and operating msg-oriented middleware

-when you create/edit a queue, you can configure the following parameters:
visibility timeout, msg retention period, delivery delay, max msg size, receive msg size, receive msg wait time, enable content-based deduplication, enable high throughput FIFO, redrive allow policy 

Short polling vs long polling 

short polling 

-when you consume msgs from a queue by using short polling, amazon sqs samples a subset of its server and return msgs from only those servers-->a particular ReceiveMessage request might not return all of your msgs. but if you got <1000 msgs in your queue, a subsequent request woll return your msgs 
if you keep consuming from your queues-->sqs samples all of its server, and you receive all your msgs 

long polling 

-reduces empty responses by letting sqs wait until a msg is available in a queue before it sends a response. unless the connection times out, the response to the ReceiveMessage request contains at least 1 of the available msgs 
in rare cases, you might receive empty responses even when a queue still contains msgs, especially if you specify a low value for the ReceiveMessageWaitTimeSeconds parameter 

-decreases false empty responses by querying all-instead of a subset of-amazon sqs servers 

-returns msgs as soon as they become available 

-https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/working-with-messages.html#setting-up-long-polling
https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html
https://aws.amazon.com/cn/sqs/faqs/
https://docs.aws.amazon.com/lambda/latest/dg/with-sqs.html


## Social Proof

[Tweet](https://twitter.com/Sandy87163104/status/1626599337500479492)
