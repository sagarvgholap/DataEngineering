# Dataframe Transformations | select Vs selectExpr


- to add a new column or modify an exsisting columns - withColumn
- to rename exsiting column - withColumnRenamed
- to drop a column - drop
- expr and its role
- select vs selectExpr

### select vs selectExpr

#### key points
- df1.select("*").show()
- df1.select("*").show()
- df1.select("*", "product_price * quantity as subtotal").show() ==> won't work
- import pyspark.sql.functions import expr
- df1.select("*", expr("product_price * quantity as subtotal")).show() ==> will work
- df1.**selectExpr**("*", "product_price * quantity as subtotal").show() ==> will work


------------------------

- df1 = products_df = toDF("product_id", "product_category_id","product_name","product_description","product_price","product_image")
- df1.show()
- df1.printSchema()
- =======
- how to increase the price by 20%
- df1.withColumn("product_price", **expr**("product_price + 1.2"))
- =======
- how to increase price for Nike with 20%, Armor with 10% and no change with other
- new_df = df1.withColumn("product_price", **expr**("case when product_name like '%Nike%' then product_price + 1.2 when product_name like '%Armour%' then product_price + 1.1 else product_price end"))


------------------------
