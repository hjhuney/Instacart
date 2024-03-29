# Instacart

An exploration of the Instacart market basket data. Full notebook can be viewed here: [Instacart Notebook](https://nbviewer.jupyter.org/github/hjhuney/Instacart/blob/master/Instacart.ipynb)

## Table of Contents

**Section 1:** [Overview](https://github.com/hjhuney/Instacart#overview)<br>
**Section 2:**  [Data Exploration](https://github.com/hjhuney/Instacart#data-exploration)<br>
**Section 3:**  [Associations](https://github.com/hjhuney/Instacart/blob/master/README.md#associations)<br>
**Section 4:**  [Recommender System Options](https://github.com/hjhuney/Instacart#recommender-system-options)<br>

## Overview

The Instacart Market Basket Analysis [dataset](https://www.kaggle.com/c/instacart-market-basket-analysis) is a popular one on Kaggle. The data consists of customer orders for an online grocery delivery company. There are several files in the dataset, approximately 50,000 products, and over 3 million customer orders. The goal is to create a recommender system to provide recommendations for customers. 

## Data Exploration

Let's do some data exploration. We'll take a look at the attributes of orders, as well as some of the most popular products. Note that for every visualization, an interactive version with more detail is available by clicking on the link below the chart. 

### Orders by Time of Day

First let's take a look at time of day for orders. 

![Time of Day](https://github.com/hjhuney/Instacart/blob/master/images/time_of_day.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/time_of_day.html)</i>

From this, we can see that most orders come in the 7am - 9pm timeframe, with heaviest demand from 9am - 5pm. 

### Orders by Day of Week

Next, we'll look at orders by day of week. 

![Day of Week](https://github.com/hjhuney/Instacart/blob/master/images/day_of_week.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/day_of_week.html)</i>

From this chart, we can see that orders are spread out reasonably well over the week, but Sunday and Monday are the busiest days, accounting for ~ 34% of all orders. Differences between Tuesday thru Saturday appear to be neglible, so we can think of the week in terms of two categories: Sunday + Monday (peak days) and Tuesday through Saturday.   

### Time Elapsed Since Prior Order

Now we'll look at days since prior order. Note that any orders over 30 days were assigned the value "30". 

![Days Since Prior Order](https://github.com/hjhuney/Instacart/blob/master/images/prev_order.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/prev_order.html)</i>

The most interesting observation here is that ~ 10% of customers reorder exactly 7 days after their prior order. Approximately 50% of customers reorder within 7 days.

### Orders by Department

Next, we'll look at product orders by departments. 

![Orders by Departments](https://github.com/hjhuney/Instacart/blob/master/images/dept.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/dept.html)</i>

Produce dominates this category, accounting for roughly 29% of all items purchased. Dairy + eggs are 2nd most popular department, accounting for ~ 17% of items purchased. 

### Most Frequently Ordered Items

Now, let's examine the most popular items. The chart below looks at the 30 most frequently purchased items from Instacart. 

![Top 30 Items](https://github.com/hjhuney/Instacart/blob/master/images/top_30_items.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/top30.html)</i>

This is one of the charts where I particularly recommend looking at the interactive version for greater detail. Regular bananas are ordered in a whopping 14% of baskets, while organic bananas are ordered in 11%. There's a significant dropoff by the time we reach the 30th most popular item (organic baby arugla), which is in 2% of baskets. Produce items dominate the top 30 products. 

### Products by Number of Times Ordered (Bins)

Let's also take a look at how often the products are ordered. There are nearly 50,000 products available, so we'll group the products into bins based on the number of times they were ordered. 

![Bins](https://github.com/hjhuney/Instacart/blob/master/images/product_bins.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/bin_chart.html)</i>

What this visualization tells us is that the majority of products are ordered between 0 - 100 times. Products ordered more than 10,000 times are rare (about 1% of total products) and even products ordered more than 2,500 times make up a small percentage (~ 5%) of the total number of products.

Items ordered 5 or fewer times account for 8.5% of total products and products ordered fewer than 20 times account for roughly 30% of products. A sizable percentage (~ 23%) of products are ordered between 100 and 500 times. 

## Associations

Let's now take a look at items that are frequently purchased with other items. We'll take a look at three popular items: organic strawberries, honeycrisp apples, and organic turkey burgers. All the charts below have interactive versions with more detailed stats included the percentage of baskets the item is purchased in ("pct_orders") and how much more likely customers purchasing the main items were more likely to purchase this additional item ("purchase ratio"). For instance a "purchase ratio" of 1.0 means a customer was exactly as likely to purcahse the item as an average customer, while a ratio of 3.2 indicates these customers were 3.2 times more likely to purchase the item than the average customer. 

### Item Sample #1: Organic Strawberries

The chart below lays out the top 30 products most frequently ordered alongside of organic strawberries. 

![Strawberries](https://github.com/hjhuney/Instacart/blob/master/images/strawberries.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/strawberry.html)</i>

In the interactive chart, we can see that 9% of customers who purchased organic strawberries also purchased organic blueberries and these customers were 3 times more likely to purchase this item than the average customer. Organic raspberries and organic string cheese were also much more likely to be purchased by these customers. 

### Item Sample #2: Honeycrisp Apples

Next, let's shift to honeycrisp apples. 

![Honeycrisp](https://github.com/hjhuney/Instacart/blob/master/images/honeycrisp.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/honeycrisp.html)</i>

One item that customers who purchase honeycrisp apples are 3.2 times more likely to purchase than the average customer is 'seedless red grapes'. These are purchased by roughly 8% of customers who bought the honeycrisp apples, but only by 2.5% of the general population. 

### Item Sample #3: Organic Turkey Burgers

Finally, let's move away from produce and shift to organic turkey burgers. 

![Turkey Burgers](https://github.com/hjhuney/Instacart/blob/master/images/turkey_burgers.svg)<br>
<i>[Click here for interactive version of chart](https://hjhuney.github.io/Instacart/html/turkey.html)</i>

This one yields very interesting results. There are several items that customers purchasing turkey burgers are more likely to purchase than the average customer including "organic baby carrots" (4.1 times more likely), "organic red bell peppers" (3.8 times more likely), "boneless skinless chicken breasts" (3.6 times more likely), and "original hummus" (3.3 times more likely).

With that, let's take a look at some possible recommender systems. 

## Recommender System Options

### Item-Based: Purchase Ratio over Average Customer

We can provide recommendations based on several factors. One methodology would be to recommend items based on our "purchase ratios" mentioned above, which shows us what items are more frequently purchased (versus the average) when a customer purchases a certain item. 

In the case of the organic turkey burgers, we found that customers were 4 times more likely to purchase baby carrots than the average customer and 3 times more likely to purchase hummus, organic red bell peppers, and boneless skinless chicken breasts. These might make good recommendations. 

I created an algorithm that took the top 100 items purchased alongside every item. Then the algorithm filters out the top 10 items based on which items the customers were most likely to purchase versus the average customer. Here were the results.

#### Turkey Burgers

We'll start out with our organic turkey burgers. 

![Turkey Burgers](https://github.com/hjhuney/Instacart/blob/master/output_images/cap_turkey.jpg)<br>


Here the top recommendations include:

* Grilled chicken breast strips (purchased 12x more than average)
* Naturals chicken nuggets (purchased 9x more than average)
* Organic chicken strips (purchased 8x more than average)

All the recommendations here also seem to pass the smell test. Do seedless raisings pair well with turkey burgers? I'm not sure, but it hardly seems outlandish. 

#### Organic Shredded Mozzarella

Next we'll look at mozzarella cheese. 

![Mozzarella](https://github.com/hjhuney/Instacart/blob/master/output_images/cap_cheese.jpg)<br>

Customers that purchased this particular mozzarella were recommended these items:

* Whole milk Ricotta cheese (purchased 20x more than average)
* Pizza sauce (purchased 19x more than average)
* Uncured pepperoni (purchased 14x more than average)

Here the recommendations seem particularly on-point, as we mostly see cheeses and pizza toppings. 


#### Lemon Hummus

Next is lemon hummus. 

![Hummus](https://github.com/hjhuney/Instacart/blob/master/output_images/cap_hummus.jpg)<br>

We find recommendations for jalapeno hummus and garlic hummus. Also many recomnendations for carrots and cheese. 

#### Blackberry Cucumber Sparkling Water

Finally, we'll take a look at blackberry cucumber sparkling water. 

![Sparkling Water](https://github.com/hjhuney/Instacart/blob/master/output_images/cap_sparkling.jpg)<br>

Every recommendation, in this instance, is another type of sparkling water. It seems that customers that purchase one flavor of sparkling water are much more likely than average to purchase another. Note that our 10th recommendation was purcahsed 20 times more than average and our top rec was purcahsed 105 times more than average. 

Overall, this methodology seems to be producing recommendations that seem reasonable. 

### Item-Based Collaborative Filtering

Another methodology would be to examine all the orders in a training set, create a sparse matrix with all products and orders (0=not purchased, 1=purchased), and find cosine similarity between all the products. From this, we'll find the most similar items. 

As an example, I developed a simple algorithm for cosine similiarity. I tested a few products; the first of which was chocolate sandwich cookies. The algorithm's top recommendations included some very similar items, such as "peanut butter cookies", "Ritz crackers", and "rice sea salt & pepper snacks". 

The results of this algorithm can be seen in the notebook, linked at the top of this page. 
