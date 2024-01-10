# Database Vs Data Warehouse Vs Data Lake

- Database:
    - is a system which holds data
    - deals majorly transactional data
    - OLTP purpose (Online Transaction Processing)
    - mainly deals with Structured data
    - deals with day to day data for better performance
    - e.g. onoine banking transaction, Oracle, SQL server, Postgress, Mysql
    - Schema on Write
        - create emp{
            empis number,
            empname string
            salary numner
        }
        while writing the insert if there is any mismatch with structure then will get an error
    - cost to store data in database is high

- Data warehouse (DWH)
    - mainly used for Analytical processing where we require a lot of historical data to find the insights.
    - The moment we run complex queries on our database with as intent to do some anaysis then your day to day transactions will become slow.
    - We take the data from databases and migrate it to datawarehouse to do analytical processing.
    - We get the data from multiple sources 
    - also deals with Structured data and mostly it is Schema on Write.
    - e.g. Teradata
    - storage cost is high but lesser than databases
    - it floows ETL process
        - supppose your data is in database
        - extract the data 
        - Transform it(is a complex process)
        - Load it ti Datawarehouse
        - this approch is complicated, reduces our flexibility since we might not able to decide what transformation are needed unless data is loaded

- Datalake
    - to get insights from huge amount of data
    - the data is preesnt in it's raw form (could be structued or unstructured)
    - e.g. Log files
        - in case of Data Warehouse we might have to transform it first and load it 
        - but with Datalake we can directly have this file in raw form in datalake
        - it follows ETL process
        - HDFS, S3 could be example of DataLake which keeps data in its raw form
        - Cost effective (cheap hardware)
        - Schema on read
            - e.g. 
                - I put a file 
                - create a structure to visualize or see the data
        - it gived you enough flexibilty
        




