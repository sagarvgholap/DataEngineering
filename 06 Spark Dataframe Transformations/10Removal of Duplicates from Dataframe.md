# Removal of Duplicates from Dataframe
- mylist = [
    (1,"KApil",34),
    (1,"KApil",34),
    (1,"Satish",26),
    (2,"Satish",26)
    ]
- df = spark.createDataFrame(mylist).toDF("id","name","age")
- df.show()
---------------

- df1 - df.distinct() **==> will consider all columns and not the subset of it**
- df1.show()

---------------

- df1 - df.select("id").distinct().show() **==> will consider only mentioned columns**

---------------

- df1 = df.dropDuplicates()
- df1 = df.dropDuplicates(["name","age"])
- 
