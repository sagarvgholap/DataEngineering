# Different ways of Dataframe Creation

- spark.read

- spark.sql
    - spark.sql("show databases").filter("namespace like 'itv005857'")
    - spark.sql("use itv005857_retail")
    - spark.sql("show tables").show()
    - orders_df = spark.sql("select * from orders_ext where order_status = 'CLOSED'")
    - orders_df.show()

- spark.table
    - df = spark.table("itv005857_retail.orders_ext")    

- spark.range(5)  
    - single col df
    - spark.range(0,8)
    - spark.range(0,8,2)
    - columns name is id

- spark.createDataFrame()
    - to create e spark df from local list
    - spark.createDataFrame(list)
    - 
        ```python
        orders_list = [
            (1,'2013-07-25 00:00:00.0',11599,'CLOSED'),
            (2,'2013-07-25 00:00:00.0',11599,'CLOSED'),
            (3,'2013-07-25 00:00:00.0',11599,'CLOSED') 

        order_raw_df = spark.createDataFrame(orders_list)
        ```
    - how to fix columns names (2 step process)
        - order_raw_df = spark.createDataFrame(orders_list).toDF('order_id','order_date','customer_id','order_status')
        - order_raw_df.show()

    - how to define col names while create dataframe(1 step process)
        - orders_schema = ['order_id','order_date','customer_id','order_status']
        - df = spark.DataFrame(orders_list, orders_schema)
        - df.printSchema()

    - how to define col names & datatypes while create dataframe
        - orders_schema = 'order_id long, order_date timestamp, customer_id int, order_status string'
        - df = spark.DataFrame(orders_list, orders_schema)
        - df.show()
        - df.printSchema()    

    - change the datatype
        - from pyspark.sql.functions import to_timestamp
        - new_df= df.withColumn("order_date",to_timestamp('order_date'))

  



















