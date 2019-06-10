# Instacart

## Overview

## Data Exploration

## Recommender System Options

### Item-Based Similarity

We can provide recommendations based on several factors. One way would be tomake recommendations based on items frequently purchased with the most recently purchased item. For instance, if our customer ordered "Honeycrisp Apples", we can find the 10 items most frequently purchased alongside this item. 

In this case, we find that bananas (regular and organic), organic strawberries, organic avocadoes, and organic baby spinach are most frequently purchased with honeycrisp apples. 


In another example, we find the items most frequently purchased with "Organic Turkey Burgers". The top 5 items includes bananas, strawberries, and hass avocados. 


The upside to this method is that we will always get frequently purchased items that pair well with the item the customer purchased. We're unlikely to get very off the wall recommendations using this system. 

The downside is that we will likely always be giving our customers similar recommendations. For instance, note that the honeycrisp apples and organic turkey burgers both generated similar recommednations for bananas and strawberries. We could find ways to negate this issue. For instance, we could randomize the top 30 items. Or we could compare the items purchased versus an "average market basket." For instance, if bananas are purchased in 15% of baskets, but only 11% of customers who order oganic turkey burgers order them, we would not want to recommend them. However, if zucchni is purchased by 8% of customer who order the turkey burgers, but only 3% of our general population, this might be a good recommendation since a much higher than average percentage of customers who order turkey burgers also order zucchini. 

### Collaborative Filtering

Another methodology would be to examine all the orders in a training set, create a sparse matrix with all products (0=not purchased, 1=purchased) and find cosine similarity between all the orders. From this, we'll find the most similar "market baskets" and we can determine what items people were most likely to purchase in these baskets. Cosine similarity would be the most obvious way to measure this, however, we could also use Jaccard similarity. 
