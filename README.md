# Third-Party Marketplace Optimization

"Foodhub" operates a fictional third party marketplace, integrating hungry customers desiring delivery with local restaurants aiming to grow sales and independent couriers looking to work flexible hours. Intense competition from established players requires Foodhub to creatively scale operations while attracting new customers, couriers, and restaurants.

This project explores Foodhub's customer demand data to uncover where potential operational problems exist, what problems are worth solving, and how the company may approach solutions.

## Business Context
Foodhub's three-sided marketplace relies on strong, consistent customer demand to satisfy customer order, courier pay, and restaurant revenue. Insights into customer demand and its relationship on delivery times will guide product prioritization across each side of the marketplace.

Customer demand may impact delivery time; however, factors such as courier supply, restaurant performance, traffic, and weather can also cause short-term performance degradation.

## Problem Statement
Foodhub currently lacks insights into customer demand data when making product and operational decisions. Without insights into customer demand, the company risks major supply imbalances across each side of the marketplace:

  * Customers face long delivery times due to low courier supply
  * Couriers face low earnings per hour resulting from low customer demand
  * Restaurants face staffing challenges in the event customer demand exceeds/lags expectations

## Solution Alignment
Solution development follows the first project from UT Austin's Postgraduate Program in Machine Learning & Artificial Intelligence for Business Applications. This solution covers the initial exploratory data analysis pre-model build. Steps completed:

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
Focusing solely on orders taking longer than 60 minutes (%>60mins) to deliver allows Foodhub to invest resources into a problem that impacts topline business metrics and each side of the marketplace. If 10% of Foodhub customers encounter delayed orders:

* Customers may lose confidence in the Foodhub platform and take their business elsewhere
* Couriers may feel their time is better spent delivering for other marketplace apps
* Restaurants may become concerned delayed orders will harm their reputation and slow revenue growth

Weekday and weekend delivery time gaps are worth exploring, though a 6 minute gap doesn't pose a foundational problem to Foodhub's operations. Cuisine preferences help uncover a deeper understanding of customers and should be explored later as the platform continues to scale. 

Foodhub is a New York based company; customers, couriers, and restaurants all have alternative options if their experience fails to meet expectations. Reducing the percentage of subpar deliveries is critical for the company's long term sustainability. Identifying root cause requires looking into each side of Foodhub's marketplace. Supply-demand imbalances, a poor app experience for couriers, or challenges with certain restaurants are among the many reasons customer orders may be late.

#### Tradeoff #2: Prioritizing problem discovery
Each side of the marketplace may play a role in delayed customer orders. Foodhub couriers, however, face an especially complex user journey where many things may go wrong. Each courier delivery includes:

* Accepting an Offer
* Traveling to a Restaurant for Order Pickup
* Waiting for Pickup at Restaurant
* Travel to Customer Location
* Drop-off Order

Foodhub's courier app must navigate supply-demand imbalances, batching, delivery distance, variance in restaurant prep time, and dispatch logic all while creating an intuititve courier app experience. Given our target metric is focused on delivery efficiency, starting discovery on the courier side of the marketplace is reasonable, but it should be paired with app instrumentation that measures each part of the courier journey.

#### Decision: Placing bets in the courier ecosystem
With limited data-driven insights into Foodhub's current operations, early problem discovery will focus on validating hypotheses and experiment design.

Three potential hypotheses on why 10% of customer orders take longer than 60 minutes to deliver:

1 - Foodhub's on-trip navigation capabilities are underperforming
Navigating New York City traffic is no small feat. Courier routes that appear optimal during certain times of the day may cause significant delays during rush hour. Foodhub's courier app may struggle to accurately predict traffic patterns or potential delays in pockets of the city.

Impact: High
Confidence: Medium
Effort: Medium/High

2 - Foodhub's pricing algorithms are disconnected from supply-demand challenges
When pricing orders, Foodhub must unpack many different nuances. Courier supply and restaurant demand may not always align on the platform. Additionally, the company likely faces margin pressure from more established competitors in the space. If Foodhub orders are not especially appealing for couriers, couriers may choose to spend their time on other apps, which harms courier supply and results in Foodhub customer orders arriving late.

Impact: High
Confidence: Low/Medium
Effort: High

3 - Foodhub's courier app provides a poor courier experience at pick-up or drop-off
Couriers must deal with constant ambiguity while using the Foodhub app. For example, restaurants may have different processes for pickup. Some customers may prefer face-to-face pickup, while others may prefer no contact drop-off. Handling all unique delivery edge cases might compete against building net-new features in the app. 

Impact: High
Confidence: Low
Effort: Medium

<Designing first experiment>
To validate Foodhub's on-trip navigation capabilities, 


## What I Learned (TBD)
* context on UTA project 1
* python for data analysis
* Exploratory Data Analysis Lifecycle - starting discovery before Data Science
