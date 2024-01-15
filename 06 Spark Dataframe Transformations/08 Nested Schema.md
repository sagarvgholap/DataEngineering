# Nested Schema
- hadoop fs -ls /public/trendytech/datasets

- hadoop fs -ls /public/trendytech/datasets/customer_nested

- hadoop fs -cat /public/trendytech/datasets/customer_nested/part-00001-950ffc21
    - 2 records
    - {"custome_id" :1, "fullname" : {"first_name":"1", "last_name":"2"} }

- hadoop fs -cat /public/trendytech/datasets/customer_nested/part-00000-950ffc21
    - 1 record

- schema ddl
    - ddlSchema = "customer_id long, fullname struct<first_name:string, last_name:string>, city string"
    - df = spark.read.format("json").schema(ddlSchema).load("/public/trendytech/datasets/customer_nested")
    - df.show()
    - df.printSchema()


- struct type
    - customer_schema = StructType(
        StructField("customer_id",LongType()),
        StructField("fullname",StructType([StructField("first_name",StringType()),StructField("last_name",StringType())]) ),
        StructField("city",StringType())
    )
    - df = spark.read.format("json").schema(customer_schema).load("/public/trendytech/datasets/customer_nested")
    - df.show()
    - df.printSchema()    

    


