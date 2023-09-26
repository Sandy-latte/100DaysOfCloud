More on Aamzon Kinesis 


## Cloud Research

Kinesis family https://aws.amazon.com/tw/kinesis/

-makes it easy to collect, process, analyse real-time streaming data so u can get timely insights 

kinesis data streams 

-the data collected is avaialble in milliseconds to enable real-time analytics use cases such as real-time dashboards, anomaly detection, dynamic pricing, and more 

kinesis firehose https://aws.amazon.com/tw/kinesis/data-firehose/?kinesis-blogs.sort-by=item.additionalFields.createdDate&kinesis-blogs.sort-order=desc

-the easiest way to reliably load streaming data into data lakes, data stores, and analytics services. it can capture, transform, and deliver streaming data to s3. redshift, elastisearch, generic HTTP endpoints, and service providers like Datadog, New Relic, MongoDB, and Splunk

-It's a fully managed service that automaticalaly scales to match the throughput of your data and requires no ongoing admin. it can also batch, compress, transform, and encrypt ur data before loading, minimising the amount of storage ussed and increasing security

kinesis data analytics 

-the easiest way to transform and analyse streaming daat in real time with Apache Flink. Apache Flink is an open source framework and engine for processing data streams 

-takes care of everything required to run streaming applications continuously, and scales automatically to match the volume and throughput of ur incoming data. with kinesiss data analytics, there are no servers to manage, no min fee for setup cost

data ingestion methods 
aws snow family 

-helps customers that need to run operations in austere, non-data centre environments, and in locas where there's lack of consistent network connectivity. the dnow family, comprised of snowcone, snowball, and snowmobile, offers a number of physical devices and capacity points, most with built-in computing capabilities

-snowcone is the smallest memeber of the snow family of edge computing and data transfer devices. snowcone is portable, rugged, and secure-smallenough to fit into a backpack and able to withstand harsh environments. customers use snowcone to deploy applications at the edge, and to collect data, process it locally, and move it to aws either offline (by shipping the device to aws) or online (by using aws datasync on snowcone to send the data to aws over the network)

the importance of data cataloging 

-building a data lake involves keeping track of all the raw assets as they were loaded into the data lake, and then tracking all of the new data assets and versions that were created by data transformation, data processing, and analytics. thus, an essential part of s3-based data lake is the data catalog. the data catalog provides a query-able interface of all assets stored in the data lake's s3 buckets 

-2 forms of a data catalog: a comprehensive data catalog that contains info about all assets that have beem ingested into the s3 data lake & a Hive Metastore Catalog (HCatalog) that contains info about data assets that have been transformed into formats and table definitions that are usable by analytics tools




