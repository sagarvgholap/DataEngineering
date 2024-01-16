# Spark Session in Detail
- its an entry point to the spark cluster
- Dataframes and Spark SQL
- Instead of having a spark context, hive context , SQL context..
    Now all of it is encapsulated in a single spark session
- we need spark context when dealing at RDD level
------------
- How to create spark session
    - 

- spark = SparkSession.\
builder.\
appName("spark session deom").\
config("spark.sql.warehouse.dir","/user/itv005857/warehouse").\
master("yarn").\
getOrCreate()

------------
- appName is to set the application name
- for any of your managed spark tables the data will be stored at directory apecified in "config"