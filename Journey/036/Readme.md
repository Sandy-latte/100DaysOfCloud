## Cloud Research-Data Lakes vs. Data Warehouses 

✍️ What is a data lake? https://aws.amazon.com/big-data/datalakes-and-analytics/what-is-a-data-lake/ 

-A centralised repository that allows you to store all your structured and unstructured data at any scale. you can just store the data as-is, without having to structure the data and run analytics 

-Survey shows that companies who implemented a Data Lake outperforming similar companies by 9% in organic revenue growth

✍️ Building big data storage solutions (data lakes) for max flexibility 

-Organisations are collecting and analysing data at a large scale, making it difficult for traditional on-premises solutions to keep pace. Amazon S3 and S3 Glacier provide an ideal storage solution for data lakes 

✍️ Data lakes vs data warehouses 

-a typical org will require both a data lakes and data warehouse as they serve different needs 

-Data warehouse: a database optimised to analyse relational data coming from transactional systems and line of business applications. the data structure, schema are defined in advance to optimise for fast sql queries, where the results are used for analysis. data is cleaned, enriched, and transformed

-Data lake: stores relational data from line of business applications, and non-relational data from IoT devices and social media. the structure of data/schema is not defined when data is captured, which means u can store your data without careful design or thinking about the questions u might want to ask in the future. organisations are seeing the benefits of data lakes and are evolving their warehouses to include data lakes

