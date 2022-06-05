<p align="center">
 <img src="https://user-images.githubusercontent.com/98360572/172027047-20043fd5-48ac-4022-a2eb-1368d1015236.png" width="50%" height="50%">
</p>


# Module 16 Challenge: Big Data - Amazon Vine Analysis
 
What exactly is meant by big data? When does data become "large"? Is it simply the size? A good rule of thumb to follow is that big data is defined as data that exceeds the capacity of operational databases.

A retail item, for example, may have hundreds of reviews but is not big data because a local machine can parse it. But if, for example, we consider that Amazon has tens of thousands of items for sale, each with hundreds of reviews. In this case, you have a case for Big Data.

---
# :one: Overview of the analysis: Explain the purpose of this analysis.

Manufacturers and publishers can get product reviews through the Amazon Vine program. Small fees are paid to Amazon by companies like SellBy, which then offer Amazon Vine users with items in exchange for a product review.

As part of this project, we had access to roughly 50 datasets. From clothing to wireless devices, each one discusses the pros and cons of a single product. The dataset selected for this analysis was **Pet Products**. After selecting the dataset, we used the PySpark Python library to perform an `ETL process` (**E**xtract, **T**ransform and **L**oad) to extract the information in the dataset, perform the neccesary transformations and load the data into `pgAdmin` via an `AWS RDS instance`.

As a further step, we then used `Python's PySpark library` to see if Amazon's Vine members are more likely to give positive evaluations of the products.

## Deliverable 1

The objective of this part is to extract the Amazon Reviews dataset and turn it into a dataframe and create four Datasets that were then loaded into tables in Amazon's AWS RDS instance.  The tools used to complete deliverable 1 were `pgAdmin` and a [`Colab` notebook](https://github.com/Peteresis/Amazon_Vine_Analysis/blob/1590370a97b909650960e773f56185a766bb2fc4/Deliverable%201/Amazon_Reviews_ETL.ipynb). 

### Tables of the datasets

|   ⚠️ **NOTE: Please click on any image to zoom**     |
| ----------- |

### D1.1 customers_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172028452-44d9522d-f8a1-4e34-9140-915cd42a47c2.png" width="20%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172028352-a4eb8b79-f2f8-433e-8335-7ffd9b764f8f.png" width="75%" height="75%">
  </div>
</div>
</p>

### D1.2 products_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172028757-5b6d989c-347e-4f16-ad53-346fce7da786.png" width="20%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172028739-46cdfd0f-17b8-4107-9f15-514518300cfa.png" width="65%" height="65%">
  </div>
</div>
</p>

### D1.3 review_id_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172028868-7922a0ab-8dae-4b7d-beb1-41a8224f5e36.png" width="40%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172028904-6a38382d-50d3-4ceb-ac52-ac1fed6f50fc.png" width="50%" height="110%">
  </div>
</div>
</p>

### D1.4 vine_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172029042-a3207a29-51f1-4e8a-97aa-43b181cad713.png" width="40%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172029049-b052e759-27da-4f6d-9dac-8e731f4805a6.png" width="50%" height="110%">
  </div>
</div>
</p>

## Deliverable 2

Using our knowledge of PySpark, Pandas, and/or SQL, we will determine if there is any bias towards reviews that were written as part of the Vine program. For this analysis, we will verify if having a paid Vine review makes a difference in the percentage of 5-star reviews that a product gets.

The tool used to complete deliverable 2 was a [`Colab` notebook](https://github.com/Peteresis/Amazon_Vine_Analysis/blob/89c49e3e299dd1c481a38d0d807c1e3a94a60f60/Deliverable%202/Vine_Review_Analysis.ipynb).

|   ⚠️ **NOTE: Please click on any image to zoom**     |
| ----------- |

### D2.1 vine_table
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029428-cdff3338-b43a-4bfe-b2d7-45cfaf92d636.png" width="50%" height="50%">
</p>

### D2.2 Filtered DataFrame where there are 20 or more total votes
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029500-737c99c3-0985-4b56-8157-a9e7d8631430.png" width="50%" height="50%">
</p>

### D2.3 Filtered DataFrame where the percentage of helpful_votes is equal to or greater than 50%
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029536-0599a4a0-29d8-4990-8cec-29926a987cf1.png" width="50%" height="50%">
</p>

### D2.4 Filtered DataFrame where there is a Vine review
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029583-5304af16-3335-48af-a063-6ca61409397a.png" width="50%" height="50%">
</p>

### D2.5 Filtered DataFrame where there isn’t a Vine review
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029611-56bdb943-760d-4fb9-9d47-318e37ee066f.png" width="50%" height="50%">
</p>

### D2.6 The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews calculated for all Vine and non-Vine reviews

### In this phase, we can calculate each partial result as a variable using functions and then conduct the total calculations using formulas. For example, to count the number of paid 5-star ratings, we may use the `filter` and `count()` functions like this:

```
paid_five_star_reviews = paid_df.filter(paid_df.star_rating == 5).count()
```

### Then, we can use a formula like the following to calculate the 5 stars review percentage:

```
paid_five_star_percent = (paid_five_star_reviews / total_paid_reviews) * 100
```

### Although there is nothing wrong with this approach, `pyspark` has powerful `SQL functions` that provide a much more elegant solution.

### After some research online, it is possible to combine the following functions of `pyspark SQL`:

* `col`: Returns a Column based on the given column name.  Source [Python pyspark.sql.functions.col() Examples](https://www.programcreek.com/python/example/98233/pyspark.sql.functions.col)
* `when`: Evaluates a list of conditions and returns one of multiple possible result expressions.  Source 
* `count`: Aggregate function: returns the number of items in a group. Source [Python pyspark.sql.functions.count() Examples](https://www.programcreek.com/python/example/98240/pyspark.sql.functions.count)
* `lit`: Creates a Column of literal value. Source [Python pyspark.sql.functions.lit() Examples](https://www.programcreek.com/python/example/98238/pyspark.sql.functions.lit)
* `groupBy`: A groupby operation involves some combination of splitting the object, applying a function, and combining the results. This can be used to group large amounts of data and compute operations on these groups. Source [pyspark.pandas.DataFrame.groupby](https://spark.apache.org/docs/latest/api/python/reference/pyspark.pandas/api/pyspark.pandas.DataFrame.groupby.html)
* `agg`: Aggregate using one or more operations over the specified axis. Source [pyspark.pandas.DataFrame.agg](https://spark.apache.org/docs/latest/api/python/reference/pyspark.pandas/api/pyspark.pandas.DataFrame.agg.html)
* `alias`: Returns a column aliased with a new name or names (in the case of expressions that return more than one column, such as explode).  Source [pyspark.sql.Column.alias](https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.sql.Column.alias.html)

### In our case, we will execute the operations directly on the `percent_votes_df` dataframe and place the outcome in the `ratings_total_df` dataframe, making the process shorter and the information easier to follow and understand.

### The output dataframe 'ratings_total_df' will have three columns and two rows.

* Column 1: `vine` it groups the two possible values from the `vine` column of the `percent_votes_df`. The only possible values are `Y` and `N`.  Code used: `percent_votes_df.groupBy("vine").agg(`  The `agg` function aggregates the operations over several axis (columns).
* Column 2: `Total_Reviews` count the total number of reviews in the `percent_votes_df` dataframe with a `Y` `vine` and the total with a `N` `vine`.  The results are written in a column named `Total_Reviews` using the alias function.  Code used: `count(col("vine")).alias("Total_Reviews")` 
* Column 3: `Total_5_Star_Reviews` uses `count`, `when`, `col` and `alias` to provide the total of 5 star ratings with the `Y` value and `N` value in `vine`.  Code used: `count(when(col("star_rating") == 5, True)).alias("Total_5_Star_Reviews")`
* Column 4: `%_5_Star_To_Total`  This column also uses `count`, `when`, `col` and `alias` and makes the calculations to provide the total percentages of 5 star ratings with the `Y` value and `N` value in `vine`.  Code used: `(count(when(col("star_rating") == 5, True))/count(col("vine"))*100).alias("%_5_Star_To_Total"))`
* Finally the function `show()` prints the output dataframe on the screen.

### The complete code is in the following block
```
from pyspark.sql.functions import col,when,count,lit
ratings_total_df = percent_votes_df.groupBy("vine").agg(
    count(col("vine")).alias("Total_Reviews"),
    count(when(col("star_rating") == 5, True)).alias("Total_5_Star_Reviews"),
    (count(when(col("star_rating") == 5, True))/count(col("vine"))*100).alias("%_5_Star_To_Total")).show()
```
### D2.6 Output Dataframe with the final results
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172030002-e3fe19f0-f388-4959-b5de-c341b1803970.png" width="50%" height="50%">
</p>

---
# :two: Results: Using bulleted lists and images of DataFrames as support, address the following questions:

## :two::one: How many Vine reviews and non-Vine reviews were there?

From Fig. D2.6 there are `170` vine reviews and `37,823` non-vine reviews.

## :two::two: How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

As shown in Fig. D2.6 there are `65` 5 stars vine reviews and `20,605` 5 stars non-vine reviews.

## :two::three:What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

Again, from Fig. D2.6, the 5 stars reviews from vine users represent `38.24%` of the total.  The 5 stars reviews fron non-vine users are `54.48%` of the total non-vine 5 stars reviews.

---
## :three: Summary: State if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.

We must keep in mind that the product category selected for this analysis was 'pet products.' In this category, vine users were less generous in giving 5 stars reviews than non-vine users, indicating that there is no bias towards 5 stars reviews from vine users. However, because the results of this analysis are only for one of Amazon's more than fifty product categories, it would be necessary to repeat the analysis in other categories to compare the results before concluding whether or not there is a bias.

---
## :four: References

**Module 16: Biga Data**, https://courses.bootcampspot.com/courses/1145/pages/16-dot-0-1-grasping-the-scope-of-big-data, :copyright: 2020-2021 Trilogy Education Services, Web 21 May 2022.

**Program Creek: Python pyspark.sql.functions() Examples**, https://www.programcreek.com/python/example/98240/pyspark.sql.functions

**Spark Apache: pyspark.pandas.DataFrame**, https://spark.apache.org/docs/latest/api/python/reference/pyspark.pandas/api/pyspark.pandas.DataFrame.html
