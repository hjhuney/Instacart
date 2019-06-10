# Instacart

Table of Contents

**Section 1:** [Overview](https://github.com/hjhuney/Instacart#overview)<br>
**Section 2:**  [Data Exploration, Part I: Orders](https://github.com/hjhuney/Instacart#data-exploration)<br>
**Section 3:**  [Data Exploration, Part II: Customer Purchases](https://github.com/hjhuney/An-Intro-to-Scala/blob/master/Part-02-Data-Types.md)<br>
**Section 4:**  [Recommender System Options](https://github.com/hjhuney/Instacart#recommender-system-options)<br>

## Overview

## Data Exploration, Part I: Order Attributes

### Orders by Time of Day

First let's take a look at time of day for orders. 

![Time of Day](https://github.com/hjhuney/Instacart/blob/master/images/time_of_day.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/time_of_day.html)</i>

From this, we can see that most orders come in the 7am - 9pm timeframe, with heaviest demand from 9am - 5pm. 

### Orders by Day of Week

Next, we'll look at orders by day of week. 

![Day of Week](https://github.com/hjhuney/Instacart/blob/master/images/day_of_week.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/day_of_week.html)</i>

From this chart, we can see that orders are spread out reasonably well over the week, but Sunday and Monday are the busiest days, account for ~ 34% of all orders. Differences between Tuesday thru Saturday appear to be neglible, so we can think of the week in terms of two categories: Sunday + Monday (peak days) and Tues - Sat.   

### Time Elapsed Since Prior Order

Now we'll look at days since prior order

![Days Since Prior Order](https://github.com/hjhuney/Instacart/blob/master/images/prev_order.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/prev_order.html)</i>

The most interesting observation here is that ~ 10% of customers reorder exactly 7 days after their prior order. Approximately 50% of customers reorder within 7 days.

### Orders by Department

![Orders by Departments](https://github.com/hjhuney/Instacart/blob/master/images/dept.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/dept.html)</i>

### Most Frequently Ordered Items


![Top 30 Items](https://github.com/hjhuney/Instacart/blob/master/images/top_30_items.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/top30.html)</i>

### Products by Number of Times Ordered (Bins)

![Bins](https://github.com/hjhuney/Instacart/blob/master/images/product_bins.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/bin_chart.html)</i>

## Data Exploration, Part II: Customers Also Purchased ... 

### Organic Strawberries

![Strawberries](https://github.com/hjhuney/Instacart/blob/master/images/strawberries.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/strawberry.html)</i>

### Honeycrisp Apples

![Honeycrisp](https://github.com/hjhuney/Instacart/blob/master/images/honeycrisp.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/honeycrisp.html)</i>

### Turkey Burgers

![Turkey Burgers](https://github.com/hjhuney/Instacart/blob/master/images/turkey_burgers.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/turkey.html)</i>

## Recommender System Options

### Item-Based Similarity

We can provide recommendations based on several factors. One way would be tomake recommendations based on items frequently purchased with the most recently purchased item. For instance, if our customer ordered "Honeycrisp Apples", we can find the 10 items most frequently purchased alongside this item. 

In this case, we find that bananas (regular and organic), organic strawberries, organic avocadoes, and organic baby spinach are most frequently purchased with honeycrisp apples. 


In another example, we find the items most frequently purchased with "Organic Turkey Burgers". The top 5 items includes bananas, strawberries, and hass avocados. 


The upside to this method is that we will always get frequently purchased items that pair well with the item the customer purchased. We're unlikely to get very off the wall recommendations using this system. 

The downside is that we will likely always be giving our customers similar recommendations. For instance, note that the honeycrisp apples and organic turkey burgers both generated similar recommednations for bananas and strawberries. We could find ways to negate this issue. For instance, we could randomize the top 30 items. Or we could compare the items purchased versus an "average market basket." For instance, if bananas are purchased in 15% of baskets, but only 11% of customers who order oganic turkey burgers order them, we would not want to recommend them. However, if zucchni is purchased by 8% of customer who order the turkey burgers, but only 3% of our general population, this might be a good recommendation since a much higher than average percentage of customers who order turkey burgers also order zucchini. 

### Collaborative Filtering

Another methodology would be to examine all the orders in a training set, create a sparse matrix with all products (0=not purchased, 1=purchased) and find cosine similarity between all the orders. From this, we'll find the most similar "market baskets" and we can determine what items people were most likely to purchase in these baskets. Cosine similarity would be the most obvious way to measure this, however, we could also use Jaccard similarity. 

### Singular Value Decomposition (SVD)

Principal components analysis (PCA). 
