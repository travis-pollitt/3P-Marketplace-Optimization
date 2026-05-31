# Third-Party Marketplace Optimization

"Foodhub" operates a fictional third party marketplace, integrating hungry customers desiring delivery with local restaurants aiming to grow sales and independent couriers looking to work flexible hours. Intense competition from established players requires Foodhub to creatively scale operations while attracting new customers, couriers, and restaurants.

This project explores Foodhub's customer demand data to uncover where potential operational problems exist, what problems are worth solving, and how the company may approach solutions.

## Business Context
Foodhub's three-sided marketplace relies on strong, consistent customer demand to satisfy customer order, courier pay, and restaurant revenue. Insights into customer demand and its relationship on delivery times will guide product prioritization across each side of the marketplace.

Customer demand may impact delivery time; however, factors such as courier supply, restaurant performance, traffic, and weather can also cause short-term performance degradation.

## Problem Statement
Foodhub currently lacks insights into customer demand data when making product and operational decisions. Without insights into customer demand, the company risks major supply imbalances across each side of the marketplace:

  * Customers face long delivery times due to low delivery person supply
  * Couriers face low earnings per hour resulting from low customer demand
  * Restaurants face staffing challenges in the event customer demand exceeds/lags expectations

## Solution Alignment
Fully leveraging Foodhub's customer demand data requires building a complex machine learning model incorporating customer demand, delivery person supply, courier pay, and restaurant availability. This analysis covers the initial exploratory data analysis pre-model build. Steps completed:

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
#### Tradeoff #1: Choosing an insight to focus on
Focusing solely on the 10% of customer orders taking longer than 60 minutes to deliver allows Foodhub to invest resources into a problem that impacts topline business meetrics and each side of the marketplace. If 10% of Foodhub customers face a poor delivery experience:

* Customers may lose confidence in the Foodhub platform and take their business elsewhere
* Couriers may feel their time is better spent delivering for other marketplace apps
* Restaurants may become concerned delayed orders will harm their reputation and slow revenue growth

Weekday and weekend delivery time gaps are worth exploring, though a 6 minute gap doesn't pose a foundational problem to Foodhub's operations. Cuisine preferences help uncover a deeper understanding of customers and should be explored later as the platform continues to scale. 

Foodhub is a New York based company; customers, couriers, and restaurants all have alternative options if their experience fails to meet expectations. Reducing the percentage of subpar deliveries is critical for the company's long term sustainability. Identifying root cause requires looking into each side of Foodhub's marketplace. Supply-demand imbalances, a poor app experience for couriers, or challenges with certain restaurants are among the many reasons customer orders may be late.

#### Tradeoff #2: Determining where to address the problem
While each side of the marketplace may be a factor in delayed orders, the first discovery decision is whether to investigate app experience issues or marketplace partnership issues. By focusing on app experience, we build a hypothesis that Foodhub's user experience or app performance is creating pain for customers. If we focus on partnerships, our hypothesis shifts toward a mismatch between courier supply, restaurant capacity, and customer demand.

Experimenting with courier pay or restaurant partnerships could improve platform participation, but those changes may also negatively impact Foodhub's margins. By contrast, investigating the app experience offers a lower-risk starting point for problem discovery. Operating a three-sided marketplace operations is complex; with limited data available, it's reasonable to hypothesize app issues may be contributing to delayed customer orders.

Focusing discovery on the Foodhub app introduces another tradeoff: starting with the customer-facing app or the courier-facing app. While both experiences may contribute delayed orders, the courier-side has a larger surface area for technical and operational problems. Couriers may struggle accepting orders, navigating to restaurants, navigating to customer locations, handoff to customers, or dealing with app performance issues. Moving across New York City is already difficult; when combined a large number of potential challenges, starting discovery on Foodhub's courier app experience makes sense.

#### Decision
Foodhub's delivery app may have user experience issues, performance issues, or some combination of the two that become simpler problems to solve.


## What I Learned (TBD)
* context on UTA project 1
* python for data analysis
* Exploratory Data Analysis Lifecycle - starting discovery before Data Science
