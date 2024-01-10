# Big Data - The Big Picture

- Data Engineering flow
    - Multiple Sources -> Ingestion -> DataLake -> Processing -> Serving
    - for Serving layer a database or a datawarehouse is the best fit

- Hadoop
    - Mysql db -> Sqoop -> HDFS -> Mapreduve/Spark -> Hive/Hbase
      employee    import   file    processing         DWH
    - when to use database/datawarehouse for serving layer 
        - whne you want to do reporting
    - when to use nosql for serving layer 
        - when you are building a custom UI

## Cloud
- Azure Cloud
    - Multiple Source -> Azure DataFactory (ADF), ADLS Gen2 -> Azure Databricks/Azure Synapse -> Azure SQL/Cosmosdb

- AWS Cloud
    - Multiple Sources -> AWS Glue -> Amazon S3 -> AWS Databricks/Athena/Redshift -> AWS RDS/Dynamodb

    
- Ingestion : Sqoop/ADF/AWS Glue
- Datalake : HDFS/ADLS Gen2/Amazon S3
- Compute : Mapreduce/Spark/Azure Databricks/Synapse/Athena/Redshift
- Serving : Hbase/Azure SQL/CosmosDB/AWS RDS/DynamoDB

## Computation / Processgin
- Serverless
    - AWS Athena
    - in case of Athen data is present in S3
    - Athena sharges you based on amount of data scanned
    - you will use resources from shared pool
    - and since resources are not dedicated you cannot get a guaranteed performance.
    - like if $5 for 1TB of data scanned then if your query scans 100 GB of data then you will be charged $0.5
    - so you have to take care that your qursy scans limited data
    - serverless will be less expensive
    - mostly used when query runs not frequently

- Serverfull
     - AWS Redshift
     - you need a dedicated cluster
     - it will charge you a lot
     - here you can get gauranteed performance
     - mostly used when query runs very frequently

- AWS
    - Athens and Redshift
    - Synapse Serverless vs Synapse Dedicated Pool

- Azure Datafactory : Ingestion
- ADLS Gen2 : for datalake storage
- Azure Databricks : for processing
- Pyspark : for processing
- Synapse : for processing
- CosmosDB : for serving
- Azure Datafactory : for Scheduling

