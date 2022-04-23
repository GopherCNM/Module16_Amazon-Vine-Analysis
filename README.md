# Big Data

## Overview of the Analysis  

In this project, we are working with a client named SellBy as they release a large catalogue of products onto an online retail format. We’ve already helped them to analyze product reviews in our module coursework. Now they’d like for us to help them determine if Amazon Vine is worth their money and time. Amazon Vine is a paid program that allows companies such as SellBy to provide product samples to Amazon Vine members in exchange for reviews. SellBy would like us to determine if there is any positivity bias in these paid reviews.  

We have been provided 50 datasets and have selected the sports dataset for the sake of this project.  Using PySpark, we performed the ETL process to extract, transform, and then load the data via an AWS RDS instance. This brings the data into a clean SQL format in pgAdmin, for further querying and analysis. We then used PySpark and Pandas to filter the data and to understand if there is any bias in the paid reviews, to help SellBy to determine if they would like to be a part of the program.  

## Results  

Using the vine_table we created for this project, we did some further filtering in PySpark to help determine if there is any positivity bias in the paid Amazon Vine reviews. Of the 4.85M total reviews in our vine_table, we filtered to show only reviews with >= 20 votes and where >= 50% of the total votes were “helpful”. This left us with a set of 61,948 reviews, from which we calculated the below counts using PySpark and Pandas filters.  

- How many Vine reviews and non-Vine reviews were there?  
Of the total 61,948 reviews, 334 were from Amazon Vine members and 61,614 were non-Vine reviews.  

**Paid Vine reviews**  
![Vine reviews](/Screenshots/VineY_DF-counts.png)  

**Non-Vine reviews**  
![non-Vine reviews](/Screenshots/VineN_DF-counts.png)  

- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?  
Of the 334 total Vine reviews, 139 were 5-star reviews. Of the 61,614 total non-Vine reviews, 32,665 were 5-star reviews.  
![5-star reviews](/Screenshots/5-star-reviews.png)  

- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?  
5-star reviews made up 41.6% of total Vine reviews and 53.0% of total non-Vine reviews.  
![5-star reviews](/Screenshots/5-star-percentages.png)  

## Summary  

In our review of the sports dataset, we see no evidence of positivity bias in Amazon Vine reviews. Our results shows that 5-star reviews in fact made up a higher portion of non-Vine reviews (53.0%) than paid Vine reviews (41.6%).  

There were 50 datasets available for analysis, and our summary is based specifically on the sports dataset. To further understand possible positivity bias for Amazon Vine reviews, we could leverage the coding we created for this project and apply it to a few of the other available datasets. We could also deepen our understanding of the distribution of ratings across the 5-star scale by getting counts for each of the 1, 2, 3, 4, and 5-star reviews. Looking at this distribution in more detail would help us to further analyze any possible positivity bias on paid Vine reviews.
