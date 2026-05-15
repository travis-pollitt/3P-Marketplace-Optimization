# Third-Party Marketplace Optimization

"Foodhub" operates a fictional third party marketplace, integrating hungry customers desiring delivery with local restaurants aiming to grow sales and independent delivery persons looking to work flexible hours. Intense competition from established players requires Foodhub to creatively scale operations while attracting new customers, drivers, and restaurants.

This project explores Foodhub's customer demand data to uncover where potential operational problems exist, what problems are worth solving, and how the company may approach solutions.

## Business Context
Foodhub's three-sided marketplace relies on strong, consistent customer demand to satisfy customer order, delivery person pay, and restaurant revenue. Insights into customer demand and its relationship on delivery times will guide product prioritization across each side of the marketplace.

Customer demand may impact delivery time; however, factors such as delivery person supply, restaurant performance, traffic, and weather can cause short-term performance degradation.

## Problem Statement
Foodhub currently lacks insights into customer demand data when making product and operations decisions. Without insights into customer demand, the company risks major supply imbalances across each side of the marketplace:

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

3 key insights emerged:
* Weekday delivery time is six minutes slower then weekend delivery time despite less traffic on the plaform.
* TBD
* TBD

## Tradeoffs and Decisions (WIP)
* Choosing an insight to focus on
* Deciding what problem is worth solving - all sides of marketplace or less?
* Sizing the opportunity
* how to approach solutions

## What I Learned (WIP)
* Build strong functional context by understanding the structure of each dataset
* Optimizing a third party marketplace brings many tradeoffs; product or operational changes may negatively impact one side of the marketplace, or the business itself. Contextulizing the existing business environment and understanding's the company's appetitite for innotivation risk is critical.
* Objectives of data analysis efforts should be clearly defined ahead of time; if not, one runs the risk of need more and more data to make a decision.
