## What is Apache Spark
- we learn't Hadoop
- it includes HDFS/Mapreduce/YARN
- where Mapreduce is biggest bottleneck
- so we use Apache Spark:
    - it is
        - General Purpose
        - In Memory
        - Compute engine
- Some people says Hadoop is dead and Spark is a replacement of Hadoop
    - this is not correct
    - since Hadoop have 3 components:
        - storage : HDFS
        - compute : MR
        - resource management : YARN
    - so, we can say that Spark is replace of only Mapreduce, since Spark is only a compute engine, so it would be liek
    - HDFS/Spark/YARN
    - but Spark is not bound to any apecific storage or resource manager
    - Spark can work with 
        - Storage : HDFS / AWS S3 / Azure ADLS Gen2/ GCS / local storage
        - Resource Manager : YARN / Mesos / Kubernetes
    - so, it's like plug and play compute engine
    - why we say Spark is General Purpose?
        - for Hadoop we need
            - Scoop for ingestion
            - for sql we need hive
            - for writing some programs we need fig
        - so we need different components to achive different things
        - so, learning curve is so big here
    - Spark says, you learn one thing and do all of them
    - In memory means and it keeps data in meomory so it is faster 

- In which language we write /Spark code?
    - Python / Scala / Java / R
    - Python is easy to learn and the support for data science is the best when we talk about python
    - Spark with python is Pyspark
    - Spark itself is written in Scala

        
- Recap:
    - 



    
