# Amazon Vine Analysis


## Overview
Amazon Vine "invites the most trusted reviewers on Amazon to post opinions about products to help their fellow customers make informed purchase decisions." The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

This analysis made use of the Sports Sales data set, accessible via download [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Sports_v1_00.tsv.gz) or access other datasets [here](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt). Each dataset contains reviews of a specific product, from clothing apparel to wireless products. The analysis used the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Using PySpark and Pandas in Google Colab Research, the dataset was analyzed to determine if bias toward favorable reviews from Vine members existed in the dataset. The findings of the dataset are outlined below. 

## Results ane Essential Questions
There is a bulleted list that addresses the three questions for unpaid and paid program reviews (7 pt)

### Essential Questions
**1. How many Vine reviews and non-Vine reviews were there?**

The total reviews, including Vine and non-Vine, is shown in the table below. The majority of the reviews are made by non-Vine users. The dataset consists of nearly 5 million reviews and Vine reviewers account for less than 1% of the total reviews. 

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineTotal1.png" width="600" />


**2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?**

The number of 5 star reviews is just over 3 million. Vine reviewers accounted for nearly 5 thousand reviews. Vine reviewers rated products as 5 Stars in 44% of reviews in this dataset. 

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineTotal2.png" width="600" />


**3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?**

In comparing Vine reviews and non-Vine reviews, Vine reviewers gave 5 star reviews 44% compared to 63% respectively for non-Vine reviewers. 

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineTotal3.png" width="600" />


# Summary: 

## Potential Positivity Bias 
Vine users do not account for a positivity bias in the dataset. Compared to non-Vine users, they are more likely to ratea product under 5 stars and they account for less than 1% of reviews, even when accounting for those reviews which are marked helpful, more likely showing near the top of reviews, they do not account for a statistically significant amount of reviews. The table below represents the number of Vine and non-Vine users, adjusted for reviews with over 50% helpful status. 

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineHelpfulAnalysis.png" width="600" />

## Recommended Further Research

To determine potential bias in the reviews of Vine users, the following are recommended
* Compare this analysis to other shopping categories to determine potential bias based on product.
* This analysis focused on positivity bias and examined reviews over 5 stars as the target. Adjusting the analysis for other star ratings may determine both positive and negative bias in reviews.


## SQL, Python, and Pandas Process

The analysis used the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin as show in the tables below. 

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/Products_Table_SQL.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/ReviewID_Table_SQL.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/Customers_Table_SQL.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/Vine_Table_SQL.png" width="600" />

After extracting the dataset, Pandas and PySpark were used to evaluate for potential bias. 

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineDF.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineFiltered20.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineFiltered50Helpful.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineNo.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/VineSummary5Star.png" width="600" />

<p align="center"><img src="https://github.com/teachjanderson/Amazon_Vine_Analysis/blob/main/Project_Images/AllReviewsVineSummary.png" width="600" />

# References
* [Amazon Vine About](https://www.amazon.com/vine/about)
* [Spark Overflow Round](https://stackoverflow.com/questions/47046827/trouble-with-pyspark-round-function)
* [Spark Examples](https://sparkbyexamples.com/pyspark/pyspark-lit-add-literal-constant/)
* [PySpark Agg](https://www.educba.com/pyspark-agg/)
* [PySpark Alias](https://www.educba.com/pyspark-alias/)