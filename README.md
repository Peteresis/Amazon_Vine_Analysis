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

The objective of this part is to extract the Amazon Reviews dataset and turn it into a dataframe and create four Datasets that were then loaded into tables in Amazon's AWS RDS instance.  The tools used to complete deliverable 1 were `pgAdmin` and a [`Colab` notebook](https://github.com/Peteresis/Amazon_Vine_Analysis/blob/1590370a97b909650960e773f56185a766bb2fc4/Deliverable%201/Amazon_Reviews_ETL.ipynb). 

### Tables of the datasets

|   ⚠️ **NOTE: Please click on any image to zoom**     |
| ----------- |

### customers_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172028452-44d9522d-f8a1-4e34-9140-915cd42a47c2.png" width="20%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172028352-a4eb8b79-f2f8-433e-8335-7ffd9b764f8f.png" width="75%" height="75%">
  </div>
</div>
</p>

### products_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172028757-5b6d989c-347e-4f16-ad53-346fce7da786.png" width="20%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172028739-46cdfd0f-17b8-4107-9f15-514518300cfa.png" width="65%" height="65%">
  </div>
</div>
</p>

### review_id_table
<p align="center">
<div class="row">
  <div class="column">
    <img src="https://user-images.githubusercontent.com/98360572/172028868-7922a0ab-8dae-4b7d-beb1-41a8224f5e36.png" width="40%" height="100%">
    <img src="https://user-images.githubusercontent.com/98360572/172028904-6a38382d-50d3-4ceb-ac52-ac1fed6f50fc.png" width="50%" height="110%">
  </div>
</div>
</p>

### vine_table
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

|   ⚠️ **NOTE: Please click on any image to zoom**     |
| ----------- |

### vine_table
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029428-cdff3338-b43a-4bfe-b2d7-45cfaf92d636.png" width="50%" height="50%">
</p>

### Filtered DataFrame where there are 20 or more total votes
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029500-737c99c3-0985-4b56-8157-a9e7d8631430.png" width="50%" height="50%">
</p>

### Filtered DataFrame where the percentage of helpful_votes is equal to or greater than 50%
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029536-0599a4a0-29d8-4990-8cec-29926a987cf1.png" width="50%" height="50%">
</p>

### Filtered DataFrame where there is a Vine review
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029583-5304af16-3335-48af-a063-6ca61409397a.png" width="50%" height="50%">
</p>

### Filtered DataFrame where there isn’t a Vine review
<p align="center">
    <img src="https://user-images.githubusercontent.com/98360572/172029611-56bdb943-760d-4fb9-9d47-318e37ee066f.png" width="50%" height="50%">
</p>







The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews (15 pt)




# :two: Results: Using bulleted lists and images of DataFrames as support, address the following questions:

## :two::one: How many Vine reviews and non-Vine reviews were there?

## :two::two: How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

## :two::three:What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?


## :three: Summary: In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.

## :four: References
