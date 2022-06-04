<p align="center">
 <img src="https://user-images.githubusercontent.com/98360572/172027047-20043fd5-48ac-4022-a2eb-1368d1015236.png" width="50%" height="50%">
</p>


# Module 16 Challenge: Big Data - Amazon Vine Analysis
 
What exactly is meant by big data? When does data become "large"? Is it simply the size? A good rule of thumb to follow is that big data is defined as data that exceeds the capacity of operational databases.

A retail item, for example, may have hundreds of reviews but is not big data because a local machine can parse it. But if, for example, we consider that Amazon has tens of thousands of items for sale, each with hundreds of reviews. In this case, you have a case for Big Data.
 
# :one: Overview of the analysis: Explain the purpose of this analysis.

Manufacturers and publishers can get product reviews through the Amazon Vine program. Small fees are paid to Amazon by companies like SellBy, which then offer Amazon Vine users with items in exchange for a product review.

As part of this project, we had access to roughly 50 datasets. From clothing to wireless devices, each one discusses the pros and cons of a single product. The dataset selected for this analysis was **Pet Products**. After selecting the dataset, we used the PySpark Python library to perform an `ETL process` (**E**xtract, **T**ransform and **L**oad) to extract the information in the dataset, perform the neccesary transformations and load the data into `pgAdmin` via an `AWS RDS instance`.

As a further step, we then used `Python's PySpark library` to see if Amazon's Vine members are more likely to give positive evaluations of the products.


## Deliverable 1

The objective of this part is to extract the Amazon Reviews dataset and turn it into a dataframe and create four Datasets that were then loaded into tables in Amazon's AWS RDS instance.  The tools used to complete deliverable 1 were `pgAdmin` and a `Colab` notebook.




# :two: Results: Using bulleted lists and images of DataFrames as support, address the following questions:

## :two::one: How many Vine reviews and non-Vine reviews were there?

## :two::two: How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

## :two::three:What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?


## :three: Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.

## :four: References
