# Converting RDD to Dataframe

1. spark.createDataFrame(rdd, schema)
    1. spark.createDataFrame(rdd).toDF(list of column names)
2. rdd.toDF(schema)    

-----------------------
- order_rdd = spark.sparkContext.textFile("{folder path}")
- order_rdd.take(5)
- new_orders_rdd = order_rdd.map(lambda x: (int(x.split(",")[0]), x.split(",")[1], int(x.split(",")[2]), x.split(",")[3]) )
- new_orders_rdd.take(5)
-----------------------
- orders_schema = 'order_id long, order_date timestamp, customer_id int, order_status string'
- df = spark.createDataFrame(new_orders_rdd, orders_schema)
- df.show()
- df.printSchema()
-----------------------
- df = spark.createDataFrame(new_orders_rdd.toDF('order_id','order_date','customer_id','order_status'))
-----------------------
- new_orders = rdd.toDF(orders_schema)