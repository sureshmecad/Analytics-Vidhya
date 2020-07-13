# AV-JanataHack-Demand-Forecasting
Approach to "Analytics Vidhya JanataHack Demand Forecasting"

Hosted at: https://datahack.analyticsvidhya.com/contest/janatahack-demand-forecasting/#ProblemStatement

Rank: 1 from 13,287 registered participant.

Solution available in jupyter notebook form.

## Problem Statement:

One of the largest retail chains in the world wants to use their vast data source to build an efficient forecasting model to predict the sales for each SKU in its portfolio at its 76 different stores using historical sales data for the past 3 years on a week-on-week basis. Sales and promotional information is also available for each week - product and store wise. 

However, no other information regarding stores and products are available. Can you still forecast accurately the sales values for every such product/SKU-store combination for the next 12 weeks accurately? If yes, then dive right in!

## Data Description:

Variable	          Definition <br />
record_ID:          Unique ID for each week store sku combination <br />
week:     	        Starting Date of the week <br />
store_id:           Unique ID for each store (no numerical order to be assumed) <br />
sku_id:             Unique ID for each product (no numerical order to be assumed) <br />
total_price:	      Sales Price of the product  <br />
base_price: 	      Base price of the product <br />
is_featured_sku:	  Was part of the featured item of the week <br />
is_display_sku:	    Product was on display at a prominent place at the store <br />
units_sold(Target): Total Units sold for that week-store-sku combination <br />

## Approach:

1. Considered this as a regression problem with 'units_sold' as a target <br />
2. Generated following new features: <br />
  (a) Count of records per 'sku-id','store-id' and combination of both <br />
  (b) Average units sold per 'sku-id','store-id' and combination of both <br />
  (c) Average base-price & total-price per 'sku-id','store-id' and combination of both <br />
  (d) Week of the year <br />
  (e) Week number from start of data <br />
  (f) Week of the month <br />
  (g) Sine & Cosine transform of week number to capture cyclic nature <br />
  (e) Price difference percent between base price & total-price <br />
3. Categorical Encoded 'sku-id' & 'store-id' with MEstimateEncoder() <br />
4. Trained the data on RandomForest & LGBM Regressor  <br />
5. Tuned the above models<br />

