# Third-Party Marketplace Optimization

"Foodhub" operates a fictional third party marketplace, integrating hungry customers desiring delivery with local restaurants aiming to grow sales and independent delivery persons looking to work flexible hours. Intense competition from established players requires Foodhub to creatively scale operations while attracting new customers, drivers, and restaurants.

This project explores Foodhub's customer demand data to uncover where potential operational problems exist, what problems are worth solving, and how the company may approach solutions.

## Business Context
Foodhub's three-sided marketplace relies on strong, consistent customer demand to satisfy customer order, delivery person pay, and restaurant revenue. Insights into customer demand and its relationship on delivery times will guide product prioritization across each side of the marketplace.

Customer demand may impact delivery time; however, factors such as delivery person supply, restaurant performance, traffic, and weather can also cause short-term performance degradation.

## Problem Statement
Foodhub currently lacks insights into customer demand data when making product and operational decisions. Without insights into customer demand, the company risks major supply imbalances across each side of the marketplace:

  * Customers facing long delivery times due to low delivery person supply
  * Delivery persons facing low earnings per hour resulting from low customer demand
  * Restaurants facing staffing challenges in the event customer demand exceeds/lags expectations

## Solution Alignment
Fully leveraging Foodhub's customer demand data requires building a complex machine learning model incorporating customer demand, delivery person supply, delivery person pay, and restaurant availability. This analysis covers the initial exploratory data analysis pre-model build. Steps completed:

#### Understanding the structure of the data
  * Data shape
  * Data types
  * Missing values
  * Statistical summary

#### Univariate analysis
  * Exploring all variables and providing observations on their distributions
  * Top 5 restaurants by order received
  * Most popular cuisine on weekends
  * % of orders costing more than 20 dollars
  * Mean order delivery time

#### Multivariate analysis
  * Relationships between numerical variables
  * Relationships between categorical variables

#### 3 key insights emerged:
* Weekday delivery time is six minutes slower then weekend delivery time despite less traffic on the plaform.
* 10% of customer orders take longer than 60 minutes to deliver.
* Indian, Italian, and Vietenemase cuisines skew towards five star reviews while remaining more popular during the week, which contradicts the broader platform's popularity on weekends.

## Tradeoffs and Decisions
Focusing solely on the 10% of customer orders taking longer than 60 minutes to deliver allows Foodhub to invest resources into a problem that impacts each side of the marketplace. If 10% of Foodhub customers face a poor delivery experience:

* Customers may become frustrated with the time it takes Foodhub orders to arrive
* Delivery persons may lose tips due to frustrated customers (even if they are not at fault) or fail to optimize their pay while delivering
* Restaurants may become concerned delayed orders will harm their reputation and slow revenue growth

Foodhub is a New York based company; customers, delivery persons, and restaurants all have alternative options if their experience fails to meet expectations. Supply/demand imbalances, a poor app experience for delivery persons, or challenges with certain restaurants are among the many reasons customer orders may be late.

Prioritizing problem discovery with limited data is challenging. Given the current constraints, starting problem discovery on the delivery person app experience enables Foodhub to solve a critical customer problem without experimenting with delivery pay or restaurant partnership deals. Foodhub's delivery app may have user experience issues, performance issues, or some combination of the two that become simpler problems to solve.


## What I Learned (TBD)
* context on UTA project 1
* python for data analysis
* Exploratory Data Analysis Lifecycle - starting discovery before Data Science
