# Amazon Vine Analysis


## Overview
Amazon Vine "invites the most trusted reviewers on Amazon to post opinions about products to help their fellow customers make informed purchase decisions." The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

This analysis made use of the Sports Sales data set, accessible via download [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Sports_v1_00.tsv.gz) or access other datasets [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt). Each dataset contains reviews of a specific product, from clothing apparel to wireless products. The analysis used the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Using PySpark and Pandas in Google Colab Research, the dataset was analyzed to determine if bias toward favorable reviews from Vine members existed in the dataset. The findings of the dataset are outlined below. 

## Results: Using bulleted lists and images of DataFrames as support, address the following questions:
There is a bulleted list that addresses the three questions for unpaid and paid program reviews (7 pt)

How many Vine reviews and non-Vine reviews were there?
How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
# Summary: 
In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
The summary states whether or not there is bias, and the results support this statement (2 pt)
An additional analysis is recommended to support the statement (2 pt)

<p align="center"><img src="https://github.com/teachjanderson/MechaCar_Statistical_Analysis/blob/main/Images/D1Variables.png" width="600" />

## SQL, Python, and Pandas Process

# References
* [Amazon Vine About](https://www.amazon.com/vine/about)
* [Spark Overflow Round](https://stackoverflow.com/questions/47046827/trouble-with-pyspark-round-function)
* [Spark Examples](https://sparkbyexamples.com/pyspark/pyspark-lit-add-literal-constant/)
* [PySpark Agg](https://www.educba.com/pyspark-agg/)
* [PySpark Alias](https://www.educba.com/pyspark-alias/)