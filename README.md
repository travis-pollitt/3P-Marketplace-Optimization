# Third-Party Marketplace Optimization

"Foodhub" operates a fictional third-party marketplace, integrating hungry customers desiring delivery with local restaurants aiming to grow sales and independent couriers looking to work flexible hours. Intense competition from established players requires Foodhub to improve marketplace reliability while attracting new customers, couriers, and restaurants.

This project explores Foodhub's customer demand data to uncover where potential operational problems exist, what problems are worth solving, and how the company approaches experimentation.

## Business Context
Foodhub's three-sided marketplace relies on strong operational rigor to satisfy customer expectations, courier pay, and restaurant revenue. Insights into customer demand and its relationship with delivery times will guide product prioritization across each side of the marketplace.

Customer demand may impact delivery time; however, factors such as courier supply, restaurant performance, traffic, and weather can also cause short-term performance degradation.

## Problem Statement
Foodhub currently lacks insights into customer demand data when making product and operational decisions. Without insights into customer demand, the company risks major supply-demand imbalances across each side of the marketplace:

  * Customers face long delivery times due to low courier supply
  * Couriers lose trust in the platform without consistent earnings per active hour
  * Restaurants face staffing challenges in the event customer demand exceeds/lags expectations

If left unaddressed, supply-demand imbalances can threaten Foodhub's on-time delivery performance and the marketplace's long-term health.

## Solution Alignment
Solution development follows the first project from UT Austin's Post Graduate Program in Machine Learning & Artificial Intelligence for Business Applications. I used exploratory data analysis to understand order volume, delivery-time distribution, cuisine demand, customer ratings, and weekday/weekend patterns.

#### 3 key insights emerged:
* Weekday delivery time is six minutes slower than weekend delivery time, despite less traffic on the platform.
* 10% of customer orders take longer than 60 minutes to deliver.
* Indian, Italian, and Vietnamese cuisines skew toward five-star reviews while remaining more popular during the week, which contrasts with the broader platform's popularity on weekends.

## Tradeoffs and Decisions
#### Tradeoff #1: Choosing an insight to focus on
Focusing solely on orders taking longer than 60 minutes (%>60mins) to deliver allows Foodhub to invest resources into a problem that impacts customer retention, courier participation, and long-term marketplace growth. If 10% of Foodhub customers encounter delayed orders:

* Customers may lose confidence in the Foodhub platform and take their business elsewhere
* Couriers may feel their time is better spent delivering for other marketplace apps
* Restaurants may become concerned delayed orders will harm their reputation and slow revenue growth

Weekday and weekend delivery time gaps are worth exploring, though a six-minute gap doesn't pose a foundational problem to Foodhub's operations. Cuisine preferences help uncover a deeper understanding of customers and should be explored later as the platform continues to scale. 

Foodhub is a New York-based company; customers, couriers, and restaurants all have alternative options if their experience fails to meet expectations. Reducing the percentage of subpar deliveries is critical for the company's long-term sustainability. Identifying root cause requires looking into each side of Foodhub's marketplace. Supply-demand imbalances, a poor app experience for couriers, or challenges with certain restaurants are among the many reasons customer orders may be late.

#### Tradeoff #2: Prioritizing problem discovery
Each side of the marketplace may play a role in delayed customer orders. Foodhub couriers, however, face an especially complex user journey where many things can go wrong. Each courier delivery includes:

* Accepting an Offer
* Traveling to a Restaurant for Order Pickup
* Waiting for Pickup at Restaurant
* Travel to Customer Location
* Drop-off Order

Foodhub's courier app manages supply-demand imbalances, batching, delivery distance, variance in restaurant prep time, and dispatch logic. Additionally, all this complexity must be displayed to couriers through an easy-to-use app. Given our target metric is focused on delivery efficiency, starting discovery on the courier side of the marketplace is reasonable, but it should be paired with app instrumentation that measures each part of the courier journey.

#### Decision: Placing bets in the courier ecosystem
With limited data-driven insights into Foodhub's current operations, early problem discovery will focus on validating hypotheses and experiment design.

Three potential hypotheses on why 10% of customer orders take longer than 60 minutes to deliver:

| Rank | Hypothesis                                                        | Impact | Confidence |    Effort   |
| :--: | ----------------------------------------------------------------- | :----: | :--------: | :---------: |
|   1  | On-trip navigation capabilities are underperforming            |  High  |   Medium   | High |
|   2  | Pricing algorithms are disconnected from supply-demand conditions |  High  | Low/Medium |     High    |
|   3  | Courier app provides a poor experience during pickup and/or drop-off |  High  |     Low    |    Medium   |


Hypothesis 1 - Foodhub's on-trip navigation capabilities are underperforming
* Navigating New York City traffic is not easy. Courier routes that appear optimal during certain times of the day may cause significant delays during rush hour. It's possible Foodhub's courier app struggles to accurately predict traffic patterns or potential delays in pockets of the city.

Hypothesis 2 - Foodhub's pricing algorithms are disconnected from supply-demand challenges
* When pricing orders, Foodhub must balance marketplace profitability with courier supply and restaurant demand. It's possible the company is underpricing customer orders, resulting in a reduced courier supply that cannot always meet customer demand. If Foodhub orders are not appealing for couriers, couriers can choose to spend their time on other apps, which harms courier supply and results in Foodhub customer orders arriving late.

Hypothesis 3 - Foodhub's courier app provides a poor courier experience at pickup or drop-off
* Couriers operate in constant ambiguity while using the Foodhub app. For example, restaurants may have different processes for pickup. Some customers may prefer face-to-face pickup, while others may prefer no-contact drop-off. Handling all unique delivery edge cases might compete against building net-new features in the app. 

To validate Foodhub's on-trip navigation capabilities, we'll instrument trip navigation and begin tracking projected versus actual courier travel times for two phases of the courier journey:

* Traveling to a Restaurant for Order Pickup
* Traveling to Customer Location

Our desired outcome for this experiment is not immediate delivery-time improvement. The first outcome focuses on observability: Foodhub successfully starts measuring projected courier travel time versus actual courier travel time for both parts of the journey. The second desired outcome is validating our first hypothesis and collecting clean data that can be segmented by delivery zone, time, restaurant, or distance. Success will be measured through three metrics:

* % of trips containing projected and actual travel time data
* % of trips where projected courier travel time is within five minutes of projected traveltime
* % of >60mins trips (delayed orders) where navigation variance > 10 minutes

Once this data is captured, Foodhub can make an informed decision on whether to invest in courier travel upgrades.

## What I Learned
Product managers often need to make early discovery decisions before analytics, data science, or engineering partners are engaged. Completing this exploratory data analysis gives me hands-on experience investigating how large datasets are structured, conducting bivariate and multivariate analysis, and writing python code to answer business questions.

Creating this product writeup challenged me to keep an open mind while conducting initial data analysis, problem discovery, and experiment design. Although this project started with a focus on Foodhub's customer demand data, the most significant insights uncovered pointed me towards the percentage of customer orders delayed by more than 60 minutes. Acknowledging the "known unknowns" is critical when defining product strategy, experiments, and execution plans.

